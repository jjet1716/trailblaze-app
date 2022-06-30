<template>
  <Header />
  <router-view></router-view>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style lang="sass">

/// fonts
/* Imbue (primary) */ 
@import url('https://fonts.googleapis.com/css2?family=Imbue:opsz,wght@10..100,300;10..100,400;10..100,500;10..100,600&display=swap')
/* Londrina Solid (secondary) */
@import url('https://fonts.googleapis.com/css2?family=Londrina+Solid:wght@100;300;400;900&display=swap')
/* Istok Web (body) */
@import url('https://fonts.googleapis.com/css2?family=Istok+Web:ital,wght@0,400;0,700;1,400&display=swap')

/// vendors (normalize)
@import assets/sass/vendors/normalize

/// abstracts (fonts, colors)
@import assets/sass/abstracts/colors-and-fonts

/// config/helper files
@import assets/sass/base

</style>
