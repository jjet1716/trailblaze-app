<template>
  <div class="page-header-container">
    <h2>Find Trails Near You in Seconds</h2>
    <Divider :width=100 :height=25 :stroke=3 :col="'#D78627'"></Divider>
    
  </div>
  <div class="form-info-container space-bottom-md">
    <p class="space-bottom-sm">Browse through thousands of outdoor recreation areas to find trails for mountain biking and hiking near you or any location you specify</p>
    <SearchTrails :submitting='loading' @find-trails="findTrails"></SearchTrails>
  </div>
  <Trails :trails="trails" :found="found"></Trails>
</template>

<script>
import SearchTrails from '../components/SearchTrails'
import Trails from '../components/Trails'
import Divider from '../components/Divider'
import axios from 'axios'

const TRAILS_API_KEY = '959c86c7a2msh639a0380e20c53ep167105jsn31c49aff3482'

export default {
  name: 'Home',
  components: {
    SearchTrails,
    Trails,
    Divider
  },
  data() {
    return {
      trails: [],
      found: 0,
      loading: false
    }
  }, 
  methods: {
    async findTrails(e) {
      this.loading = true
      // console.log(e.trail_type)
      // console.log(e.address)

      // make trails API call (need to hide key from frontend eventually)
      try {
        const res = await axios({
          method: 'get',
          url: 'https://trailapi-trailapi.p.rapidapi.com/trails/explore/',
          params: {
            lat: e.lat, 
            lon: e.long,
            radius: e.radius
          },
          headers: {
            'X-RapidAPI-Key': TRAILS_API_KEY,
            'X-RapidAPI-Host': 'trailapi-trailapi.p.rapidapi.com'
          }
        })

        this.trails = res.data.data
        this.found = this.trails.length

        console.log(this.trails, this.found)

      } catch(err) {
        console.log(err)
      }
      this.loading = false
    }
  }
}
</script>

<style lang="sass" scoped>
  @import ../assets/sass/pages-shared
</style>