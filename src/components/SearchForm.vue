<template>
    <form action="" methods="POST">
        <select name="type">
            <option>Mountain Biking</option>
            <option>Hiking</option>
        </select>
        <label><input name="radius" /></label>
        <label><input name="location" /></label>
    </form>
</template>

<script>
    export default {
        name: 'SearchForm',
    }
</script>

<style lang="sass">
    @import ../assets/sass/search-form
</style>