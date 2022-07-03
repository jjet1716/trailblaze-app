<template>
  <Header></Header>
  <main class="tb-page">
    <div class="content-wrapper">
      <router-view></router-view>
    </div>
  </main>
  <Footer></Footer>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Header,
    Footer
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

/// config/helper files
@import assets/sass/base

/// root settings
html
    background-image: url("assets/images/topographic-background.svg")
    background-attachment: fixed
    @include font-body
    line-height: 1.35
    -webkit-font-smoothing: antialiased
    -moz-osx-font-smoothing: grayscale

    ::selection
        background: $color-brown
        color: white

</style>
