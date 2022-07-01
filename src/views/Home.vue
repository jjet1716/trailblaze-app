<template>
  <div class="page-header-container">
    <h2>Find Trails Near You in Seconds</h2>
    <div class="divider-container">
      <svg width="100%" height="17" viewBox="0 0 1115 17" fill="none" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
        <path d="M1.75486 8.20546C19.9889 -17.2316 -5.3694 36.3376 17.419 6.56303L1114.5 6.56302" stroke="#D78627" stroke-width="3"/>
      </svg>
    </div>
    
  </div>
  <div class="form-info-container space-bottom-md">
    <p class="space-bottom-sm">Browse through thousands of outdoor recreation areas to find trails for mountain biking and hiking near you or any location you specify</p>
    <SearchTrails></SearchTrails>
  </div>
  <Trails :trails="trails"></Trails>
</template>

<script>
import SearchTrails from '../components/SearchTrails'
import Trails from '../components/Trails'

export default {
  name: 'Home',
  components: {
    SearchTrails,
    Trails
  },
  data() {
    return {
      trails: []
    }
  }, 
  created() {
    this.trails = [
      {
        name: 'Maybury',
        distance: '7.0 miles',
        location: 'Northville, Michigan USA',
        difficulty: 'intermediate',
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
      },
      {
        name: 'Tree Farm',
        distance: '11.0 miles',
        location: 'Novi, Michigan USA',
        difficulty: 'challenging',
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
      },
      {
        name: 'Hickory Glen',
        distance: '6.0 miles',
        location: 'Commerce Township, Michigan USA',
        difficulty: 'easy',
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
      }
    ]
  }
}
</script>

<style lang="sass" scoped>
  @import ../assets/sass/pages-shared
</style>