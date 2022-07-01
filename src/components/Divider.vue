<template>
    <div class="divider-container">
        <svg v-bind:width="width + '%'" v-bind:height="height" viewBox="0 0 1115 17" fill="none" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMinYMid slice">
            <path d="M1.75486 8.20546C19.9889 -17.2316 -5.3694 36.3376 17.419 6.56303L1114.5 6.56302" v-bind:stroke="col" v-bind:stroke-width="stroke"/>
        </svg>
    </div>
</template>

<script>
export default {
    name: 'Divider',
    props: {
        width: {
            type: Number,
            default: 100
        },
        height: {
            type: Number,
            default: 25
        },
        stroke: {
            type: Number,
            default: 3
        },
        col: {
            type: String,
            default: "#D78627"
        }
    }
}
</script>
