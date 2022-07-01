<template>
  <div class="page-header-container">
    <h2>Find Trails Near You in Seconds</h2>
    <Divider :width="100" :height="25" stroke="3" :col="'#D78627'"></Divider>
    
  </div>
  <div class="form-info-container space-bottom-md">
    <p class="space-bottom-sm">Browse through thousands of outdoor recreation areas to find trails for mountain biking and hiking near you or any location you specify</p>
    <SearchTrails @find-trails="findTrails"></SearchTrails>
  </div>
  <Trails :trails="trails" :found="found"></Trails>
</template>

<script>
import SearchTrails from '../components/SearchTrails'
import Trails from '../components/Trails'
import Divider from '../components/Divider'

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
      found: 0
    }
  }, 
  created() {
    // does something when component is created
  },
  methods: {
    findTrails(e) {
      console.log(e.trail_type)
      console.log(e.radius)
      console.log(e.location)

      // make api call here

      // test data for now
      this.found = 3
      this.trails = [
      {
        name: 'Maybury',
        url: "https://www.singletracks.com/bike-trails/maybury/",
        length: "7.0",
        description: "Half of the trail is fast and moderately hilly. The other half is tight/winding single track. Bike trail is closed from December 15 through April 15 and signs claim the park closes at dusk. This 4 mile loop is a great place to practice your spinning, not to mention your technical skills on sudden, short climbs and winding singletrack.",
        difficulty: 'intermediate',
        city: "Northville",
        region: "Michigan",
        country: "USA",
        thumbnail: "https://images.singletracks.com/blog/wp-content/uploads/2009/11/maybury10-31-9_1565-0-orig.jpg"
      },
      {
        name: 'Tree Farm',
        url: "https://www.singletracks.com/bike-trails/novi-tree-farm-lakeshore-park/",
        length: "11.0 miles",
        description: "Starts on right hand side and is all pure sweet single track. It is technical and has many manmade stunts(rockgardens, log jumps) with bypass at each. The main feature is \"THE CRATER\". Which is a popular spot to stop and do some jumping and hucking. Opportunity to get sweet air.",
        difficulty: 'challenging',
        city: "Novi",
        region: "Michigan",
        country: "USA",
        thumbnail: ""
      },
      {
        name: 'Hickory Glen',
        url: "https://www.singletracks.com/bike-trails/hickory-glen/",
        length: "6.0 miles",
        description: "The trail loop is 5.7 miles. Look for yellow arrows (some at eye level and some higher) pointing you in the correct direction of the trail loop. Carsonite-type ground markers have also been installed and blacktop path intersections to clarify the MTB trail direction. The trail makes its way around most of Hickory Glen Park and at about the 4 mile mark you'll find yourself back on the blacktop bike path heading towards the EAST end of the park. You'll cross over a very nice floating bridge and board walk, and just after you are over the board walk the trail picks back up on the left. After you finish this section of trail, you can pick up the MTB trail again on the EAST side of the blacktop path. After a quarter mile you'll be dumped back on the blacktop path. Take it back over the floating bridge and pick up the MTB trail on your left again and follow back to the trailhead.",
        difficulty: 'easy',
        city: "Commerce Township",
        region: "Michigan",
        country: "USA",
        thumbnail: "https://images.singletracks.com/blog/wp-content/uploads/2017/08/mobile-1502592161-orig.jpg"
      },
      {
        name: 'Hickory Glen',
        url: "https://www.singletracks.com/bike-trails/hickory-glen/",
        length: "6.0 miles",
        description: "The trail loop is 5.7 miles. Look for yellow arrows (some at eye level and some higher) pointing you in the correct direction of the trail loop. Carsonite-type ground markers have also been installed and blacktop path intersections to clarify the MTB trail direction. The trail makes its way around most of Hickory Glen Park and at about the 4 mile mark you'll find yourself back on the blacktop bike path heading towards the EAST end of the park. You'll cross over a very nice floating bridge and board walk, and just after you are over the board walk the trail picks back up on the left. After you finish this section of trail, you can pick up the MTB trail again on the EAST side of the blacktop path. After a quarter mile you'll be dumped back on the blacktop path. Take it back over the floating bridge and pick up the MTB trail on your left again and follow back to the trailhead.",
        difficulty: 'easy',
        city: "Commerce Township",
        region: "Michigan",
        country: "USA",
        thumbnail: "https://images.singletracks.com/blog/wp-content/uploads/2017/08/mobile-1502592161-orig.jpg"
      },
      {
        name: 'Maybury',
        url: "https://www.singletracks.com/bike-trails/maybury/",
        length: "7.0",
        description: "Half of the trail is fast and moderately hilly. The other half is tight/winding single track. Bike trail is closed from December 15 through April 15 and signs claim the park closes at dusk. This 4 mile loop is a great place to practice your spinning, not to mention your technical skills on sudden, short climbs and winding singletrack.",
        difficulty: 'intermediate',
        city: "Northville",
        region: "Michigan",
        country: "USA",
        thumbnail: "https://images.singletracks.com/blog/wp-content/uploads/2009/11/maybury10-31-9_1565-0-orig.jpg"
      },
      {
        name: 'Tree Farm',
        url: "https://www.singletracks.com/bike-trails/novi-tree-farm-lakeshore-park/",
        length: "11.0 miles",
        description: "Starts on right hand side and is all pure sweet single track. It is technical and has many manmade stunts(rockgardens, log jumps) with bypass at each. The main feature is \"THE CRATER\". Which is a popular spot to stop and do some jumping and hucking. Opportunity to get sweet air.",
        difficulty: 'challenging',
        city: "Novi",
        region: "Michigan",
        country: "USA",
        thumbnail: ""
      }
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
  @import ../assets/sass/pages-shared
</style>