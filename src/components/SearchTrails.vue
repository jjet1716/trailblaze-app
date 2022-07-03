<template>
    <!-- put error message here -->
    <form @submit="findTrails" id="find-trails">
        <div class="col-layout space-bottom-sm full-mobile">
            <label for="trail-type" class="col--2 flex-col">Trail Type
                <select id="trail-type" v-model="trail_type" name="trail_type" required>
                    <option value="biking">Mountain Biking</option>
                    <option value="hiking">Hiking</option>
                </select>
            </label>
            <label for="radius" class="col--2 flex-col">Radius (miles)
                <input type="number" id="radius" v-model="radius" name="radius" placeholder="25"/>
            </label>
        </div>
        <div class="col-layout space-bottom-sm">
            <label for="autocomplete" class="flex-col grow--1">Location Address
                <input type="text" id="autocomplete" v-model="address" name="location" required/>
            </label>
            <button @click="setCurrentLocation()" type="button" id="cur-location-btn" class="btn btn-primary" v-bind:class="{'spinner active': spinning}">
                <i v-bind:style="[ spinning ? {'opacity' : '0'} : {'opacity' : '1'} ]" class="fas fa-location-dot"></i>
            </button>
        </div>
        <button type="submit" class="btn btn-primary" v-bind:class="{'spinner active': submitting}"><span v-bind:style="[ submitting ? {'opacity' : '0'} : {'opacity' : '1'} ]">Find Trails</span></button>
    </form>
</template>

<script>
import axios from 'axios'
const GOOGLE_MAPS_API_KEY = 'AIzaSyD_aJ7n1ZNpYNAESNADXPIR6CAgSJsAyxs'

export default {
    name: 'SearchTrails',
    props: {
        submitting: {
            type: Boolean,
            default: false
        },
    },  
    data() {
        return {
            trail_type: 'biking', // default setting for trail type
            radius: '25', // default radius
            address: '',
            lat: '',
            long: '',
            spinning: false, // true when pin button is pressed (activates css spinner)
        }
    },
    mounted() {
        // instantiate autocomplete when DOM is ready
        let autocomplete = new google.maps.places.Autocomplete(
            document.getElementById('autocomplete')
        )

        autocomplete.addListener("place_changed", () => {
            let place = autocomplete.getPlace()
            this.lat = place.geometry.location.lat()
            this.long = place.geometry.location.lng()
            this.address = place.formatted_address
        })

        // listen for custom address entry
        document.getElementById('autocomplete').addEventListener("input", (e) => {
            this.lat = '' // needs to be recomputed
            this.long = '' // needs to be recomputed
            this.address = e.target.value
        })
    },
    methods: {
        findTrails(e) {
            e.preventDefault()

            if (this.lat === '' || this.long === '') { // custom addr entered (not provided by google)
                this.addressToCoords(this.address)
                    .then(res => {
                        // set coords from custom address if not false
                        if (res === false) {
                            // show error to user here
                            console.log('Address could not be found')
                            return false
                        }
                        this.lat = res.lat
                        this.long = res.long
                        this.$emit('find-trails', this)
                    })
            } else {
                this.$emit('find-trails', this)
            }
        },
        setCurrentLocation() {
            this.spinning = true
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    position => { // user accepts location prompt
                        this.lat = position.coords.latitude
                        this.long = position.coords.longitude
                        this.coordsToAddress(this.lat, this.long)
                            .then(res => {
                                // add address to input field, have backup be coords for now...
                                this.address = res === false ? (this.lat + ', ' + this.long) : res
                            })
                        this.spinning = false
                        //this.customAddr = false
                    },
                    error => { // user does not accept location prompt
                        console.log(error.message)
                        this.spinning = false
                    }
                )
            } else {
                alert('Your browser does not support location services')
                this.spinning = false
            }
        },
        async coordsToAddress(lat, long) {
            // convert coords to address from gmaps geocode api, if error return false 
            try {
                const res = await axios({
                    method: 'get',
                    url: 'https://maps.googleapis.com/maps/api/geocode/json',
                    params: {
                        latlng: lat + ',' + long,
                        key: GOOGLE_MAPS_API_KEY
                    }
                })

                if (res.data.error_message) {
                    console.log(res.data.error_message)
                    return false
                } else {
                    console.log(res.data.results[0].formatted_address)
                    return res.data.results[0].formatted_address
                }

            } catch(err) {
                console.log(err.message)
                return false
            }
        },
        async addressToCoords(address) {
            // convert address to coords from gmaps geocode api, if error return false 
            try {
                const res = await axios({
                    method: 'get',
                    url: 'https://maps.googleapis.com/maps/api/geocode/json',
                    params: {
                        address: address,
                        key: GOOGLE_MAPS_API_KEY
                    }
                })

                if (res.data.status !== "OK") {
                    console.log(res.data.status)
                    return false
                } else {
                    console.log(res.data.results[0])
                    return { lat: res.data.results[0].geometry.location.lat, long: res.data.results[0].geometry.location.lng }
                }

            } catch(err) {
                console.log(err.message)
                return false
            }
        }
    }
}
</script>

<style lang="sass">
    @import ../assets/sass/base
    @import ../assets/sass/search-trails
    @import ../assets/sass/buttons
</style>