<template>
    <header>
        <div class="header-col">
            <div class="logo-container">
                <img alt="Trailblaze logo" src="../assets/images/trailblaze-logo.svg" />
            </div>
            <h1>Trailblaze</h1>
        </div>
        <div class="header-col">
            <nav>
                <ul id="main-nav">
                    <li><router-link to="/about">About</router-link></li>
                    <li><router-link to="#">Sign In</router-link></li>
                    <li><router-link to="/contact">Contact</router-link></li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="sass">
    @import ../assets/sass/header
</style>