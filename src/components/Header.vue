<template>
    <header>
        <div class="content-wrapper">
            <div class="header-col logo">
                <div class="logo-container">
                    <router-link to="/"><img alt="Trailblaze logo" src="../assets/images/trailblaze-logo.svg" /></router-link>
                </div>
                <router-link to="/"><h1>Trailblaze</h1></router-link>
            </div>
            <div class="header-col nav">
                <nav>
                    <ul id="main-nav">
                        <li><router-link to="/about">About</router-link></li>
                        <li><a @click="comingSoon()" href="">Sign In</a></li>
                        <li><a @click="comingSoon()" href="">Contact</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    comingSoon() {
        alert("More pages coming soon")
    }
  }
}
</script>

<style lang="sass">
    @import ../assets/sass/abstracts/colors-and-fonts
    @import ../assets/sass/header
</style>