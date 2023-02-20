<template>
  <main class="container">
    <Header/>
    <Hero />
    <Education/>
    <!-- <Project /> -->
    <Skill />
    <p class="copyright">&copy; This website created by Nguyen Vinh Tieng (2022) 
      <!-- <a target="_blank" rel="noopener noreferrer" href="https://www.facebook.com/nvinhtieng/">facebook</a> -->
    </p>
  </main>
  <BackgroundAnimation />
</template>

<script>
import Hero from './components/Hero.vue'
import Header from './components/Header.vue'
import Education from './components/Education.vue'
// import Project from './components/Project.vue'
import Skill from './components/Skill.vue'
import BackgroundAnimation from './components/BackgroundAnimation.vue'
export default {
  name: 'App',
  components: {
    Hero,
    Header,
    Education,
    // Project,
    Skill,
    BackgroundAnimation
  },
  mounted() {
    document.title = "❣️Vinh Tieng | Portfolio❣️";
  },
}
</script>

<style>
  @import "./assets/styles/_reset.scss";
  @import "./assets/styles/_fonts.scss";
  @import "./assets/styles/_global.scss";
</style>
