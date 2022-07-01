<template>
    <div class="col-layout space-bottom-sm">
        <p id="results-found" class="shrink--0">{{ found }} results found</p>
        <Divider :width="100" :height="17" stroke="2" :col="'#D78627'"></Divider>
    </div>

    <div class="trail-grid-container">
        <div v-for="trail in trails" class="trail-item">
            <Trail :trail="trail"></Trail>
        </div>  
    </div>
    
</template>

<script>
import Trail from './Trail'
import Divider from '../components/Divider'

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
        Trail,
        Divider
    }
}
</script>

<styles lang="sass">
    @import ../assets/sass/abstracts/colors-and-fonts
    @import ../assets/sass/trails
    @import ../assets/sass/buttons
</styles>