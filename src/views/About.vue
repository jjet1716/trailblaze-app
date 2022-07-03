<template>
    <div class="page-header-container">
        <h2>About Me</h2>
        <Divider :width="100" :height="25" stroke="3" :col="'#D78627'"></Divider>
    </div>
    <div>
        <div id="bio-container">
            <p>Hello, my name is Joseph Nagy. I am a senior Computer Science Engineering student at Michigan State University and I 
            enjoy building for the web on the front-end. I have been creating websites, specifically for Municipalities and small 
            businesses, for over a year now and some of the clients I have worked with include the 
            <a href="https://dewittmi.gov/" target="_blank">City of DeWitt</a>,<a href="https://www.natat.org/" target="_blank">NATaT</a>,
            and the <a href="https://oldtown-generalstore.com/" target="_blank">Oldtown General Store</a>.</p>
            <p>Some of my technical skills include:</p>
            <ul id="skills">
                <li>Front-end frameworks - Angular, Flask</li>
                <li>Programming Languages - TypeScript/JavaScript, PHP, HTML/CSS, Python, C++</li>
                <li>Tools - Visual Studio Code, WordPress, Dreamweaver, Figma</li>
            </ul>
            <p>In my free time, I enjoy Mountain Biking, Rock Climbing, playing Valorant/Overwatch, and doing random fun things with my family.</p>
        </div>
    </div>
</template>

<script>
import Divider from '../components/Divider'

export default {
    name: 'About',
    components: {
        Divider
    }
}
</script>

<style lang="sass" scoped>
    @import ../assets/sass/base
    @import ../assets/sass/pages-shared
</style>