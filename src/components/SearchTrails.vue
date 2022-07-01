<template>
    <form @submit="findTrails" id="find-trails">
        <div class="col-layout space-bottom-sm">
            <label for="trail-type" class="col--2 flex-col">Trail Type
                <select id="trail-type" v-model="trail_type" name="trail_type" required>
                    <option value="hiking">Hiking</option>
                    <option value="biking">Mountain Biking</option>
                </select>
            </label>
            <label for="radius" class="col--2 flex-col">Radius (mi)
                <input type="number" id="radius" v-model="radius" name="radius" placeholder="25"/>
            </label>
        </div>
        <div class="col-layout space-bottom-sm">
            <label for="location" class="flex-col grow--1">Location Address
                <input type="text" id="location" v-model="location" name="location" required/>
            </label>
            <button @click="getCurrentLocation()" type="button" id="cur-location-btn" class="btn btn-primary">
                <i class="fas fa-location-dot"></i>
            </button>
        </div>
        <button type="submit" class="btn btn-primary">Find Trails</button>
    </form>
</template>

<script>
    export default {
        name: 'SearchTrails',
        data() {
            return {
                trail_type: 'hiking',
                radius: '25',
                location: ''
            }
        },
        methods: {
            findTrails(e) {
                e.preventDefault()
                this.$emit('find-trails', this)
            },
            getCurrentLocation() {
                alert("Location services coming soon!")
            }
        }

    }
</script>

<style lang="sass">
    @import ../assets/sass/abstracts/colors-and-fonts
    @import ../assets/sass/search-trails
    @import ../assets/sass/buttons
</style>