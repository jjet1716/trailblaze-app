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
                        <li><router-link to="#">Sign In</router-link></li>
                        <li><router-link to="/contact">Contact</router-link></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="sass">
    @import ../assets/sass/abstracts/colors-and-fonts
    @import ../assets/sass/header
</style>