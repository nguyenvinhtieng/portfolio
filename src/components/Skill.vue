<template>
  <section class="skills">
    <h2 class="ttl">My skills & tools 🛠️</h2>
    <div class="skill__ability">
      <div class="skill__ability-item basic">
        <span class="skill__ability-txt">Basic</span>
      </div>
      <div class="skill__ability-item medium">
        <span class="skill__ability-txt">Medium</span>
      </div>
      <div class="skill__ability-item strong">
        <span class="skill__ability-txt">Strong</span>
      </div>
      <div class="skill__ability-item master">
        <span class="skill__ability-txt">Master</span>
      </div>
    </div>
    <div class="skill__list">
      <div v-for="skill in skills" :item="skill" :key="skill"  :class="['skill__item', skill.level]">
        <div class="skill__img">
          <img :src="`/${skill.img}`" :alt="skill.name">
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import skills from "../constants/skills";
export default {
  name: "Skill",
  data() {
    return {
      skills: []
    }
  },
  mounted() {
    this.skills = skills;
  },
};
</script>
<style>
@import "../assets/styles/_skill.scss";
</style>
