<template>
    <div class="page-header-container">
        <h2>About Page</h2>
        <div class="divider-container">
            <svg width="100%" height="17" viewBox="0 0 1115 17" fill="none" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
                <path d="M1.75486 8.20546C19.9889 -17.2316 -5.3694 36.3376 17.419 6.56303L1114.5 6.56302" stroke="#D78627" stroke-width="3"/>
            </svg>
        </div>
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
export default {
  name: 'About',
}
</script>

<style lang="sass" scoped>
  @import ../assets/sass/pages-shared
</style>