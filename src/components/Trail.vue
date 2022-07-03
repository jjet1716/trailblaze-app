<template>
    <div class="card-layout flex-col">
        <a v-bind:href='trail.url' target="_blank" rel="noopener">
            <div v-bind:style="{ 'background-image': 'url(' + trail.thumbnail + ')' }" v-bind:class="[this.trail.thumbnail ? 'image' : 'no-image', 'trail-image-container']">
                <p v-if="trail.difficulty" class="difficulty-tax" :class="[difficultyToColor(trail.difficulty)]">{{ trail.difficulty }}</p>
            </div>
        </a>

        <div class="trail-data-container">
            <a v-bind:href='trail.url' class="trail-name" target="_blank" rel="noopener">{{ trail.name }}</a>
            <div class="meta-data space-bottom-xsm">
                <p>{{ trail.city }}, {{ trail.region }}, {{ trail.country }}</p>
                <p>{{ trail.length }} Miles</p>
            </div>
            <p>{{ trimDescription() }}</p>
        </div>

        <button class="btn btn-primary" @click="redirectToTrail()">Read More</button>
    </div>
    
</template>

<script>
export default {
    name: "Trail",
    props: {
        trail: Object
    },
    methods: {
        redirectToTrail() {
            window.open(this.trail.url, '_blank')
        },
        trimDescription() {
            return (this.trail.description).substring(0, 100).replaceAll(/(<br>)|(<br \/>)|(<br\/>)/g, '') + '...'
        },
        difficultyToColor(diff) {
            const diffToColor = {
                'Challenging' : 'red',
                'Advanced' : 'red',
                'Intermediate' : 'yellow',
                'Beginner' : 'green',
                'Easy' : 'green',
                'Easiest' : 'green'
            }

            if (diff in diffToColor) {
                return diffToColor[diff]
            } 

            return ''
        }
    }
}
</script>