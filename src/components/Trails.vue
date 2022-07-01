<template>
    <div class="col-layout">
        <p id="results-found">{{ found }} results found</p>
        <div class="divider-container grow--1">
            <svg width="100%" height="17" viewBox="0 0 1115 17" fill="none" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
                <path d="M1.75486 8.20546C19.9889 -17.2316 -5.3694 36.3376 17.419 6.56303L1114.5 6.56302" stroke="#D78627" stroke-width="3"/>
            </svg>
        </div>
    </div>

    <div v-for="trail in trails">
        <Trail :trail="trail"></Trail>
    </div>
</template>

<script>
import Trail from './Trail'

export default {
    name: "Trails",
    props: {
        found: {
            type: Number,
            default: 0
        },
        trails: {
            type: Array,
            default: []
        }
    },
    components: {
        Trail
    }
}
</script>

<styles lang="sass">
    @import ../assets/sass/abstracts/colors-and-fonts
    @import ../assets/sass/trails
    @import ../assets/sass/buttons
</styles>