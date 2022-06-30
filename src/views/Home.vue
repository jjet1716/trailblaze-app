<template>
    <h2>Find Trails Near You in Seconds</h2>
    <svg width="1115" height="17" viewBox="0 0 1115 17" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M1.75486 8.20546C19.9889 -17.2316 -5.3694 36.3376 17.419 6.56303L1114.5 6.56302" stroke="#D78627" stroke-width="2"/>
    </svg>
    <p>
        Browse through thousands of outdoor recreation areas to find trails for mountain biking and hiking near you or any location you specify
    </p>
    <SearchForm></SearchForm>
</template>

<script>
import SearchForm from '../components/SearchForm'

export default {
  name: 'Home',
  components: {
    SearchForm
  }
}

</script>