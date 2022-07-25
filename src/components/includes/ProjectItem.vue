<template>
  <div class="project__card">
    <div class="project__img">
      <img :src="`/images/projects/${project.image}`" :alt="project.name">
    </div>
    <div class="project__content">
      <h3 class="project__name txt__gradient-blue">{{project.name}}</h3>
      <p class="project__desc">{{project.description}}</p>
      <div class="project__tech">
        <span v-for="tech in project.technology" :key="tech"  class="project__tech-item">
          <span class="project__tech-txt">
            {{tech}}
          </span>
        </span>
      </div>
    </div>
    <div class="project__link">
      <a v-if="project.github" :href="project.github" class="project__link-item github" target="_blank">
        <div class="project__link-ico">
          <ion-icon name="logo-github"></ion-icon>
        </div>
        <div class="project__link-txt">
          Github 
        </div>
      </a>
      <a v-if="project.demo" :href="project.demo" class="project__link-item demo" target="_blank">
        <div class="project__link-ico">
          <ion-icon name="easel-outline"></ion-icon>
        </div>
        <div class="project__link-txt">
          Demo 
        </div>
      </a>
    </div>
  </div>
</template>
<script>
export default {
  name: "ProjectItem",
  props: {
    project: {
      type: Object,
      required: true
    }
  },
  mounted() {
    console.log(this.project)
  },
}
</script>