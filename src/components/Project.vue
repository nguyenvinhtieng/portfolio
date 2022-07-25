<template>
  <section class="project">
    <h2 class="ttl">My coding project 👨‍💻  </h2>
    <div class="project__list">
      <carousel :settings="settings" :breakpoints="breakpoints">
        <slide v-for="project in projects" :key="project">
          <ProjectItem :project="project" />
        </slide>
        <template #addons>
          <navigation />
          <pagination />
        </template>
      </carousel>
    </div>
  </section>
</template>
<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';
import projects from "../constants/projects"
import ProjectItem from "./includes/ProjectItem.vue"
export default {
  name: "Project",
  data() {
    return {
      settings: {
				itemsToShow: 1,
				snapAlign: "center",
        wrapAround: "true"
			},
			breakpoints: {
				700: {
					itemsToShow: 2.5,
					snapAlign: "center"
				},
      },
      projects: []
    }
  },
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
    ProjectItem
  },
  mounted() {
    this.projects = projects
  },
};
</script>
<style>
  @import "../assets/styles/_project.scss";
</style>