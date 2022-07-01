<template>
    <p>{{ trail.name }}</p>
</template>

<script>
export default {
    name: "Trail",
    props: {
        trail: Object
    }
}
</script>