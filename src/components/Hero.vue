<template>
  <section class="hero">
    <div class="hero__content">
      <p class="hero__content-hi">HI, MY NAME IS</p>
      <h1 class="txt__gradient-blue">{{name}}</h1>
      <h2 class="hero__content-iam">
        <span>I am a </span>
        <span class="txt__gradient-orange hero__content-job" ref="job">Frontend Developer</span>
      </h2>
      <p class="hero__content-intro">
        I like to build amazing websites for humans 💻💻. Currently, I'm focusing on improving my coding skills in HTML CSS, and Vuejs 🔥🔥. In another hand I'm learning Node js to have knowledge about Back-end, I hope in the shortest time I can become a full-stack developer (Maybe 5 to 7 years later 😂😂)
      </p>
      <p class="hero__content-intro">
        In my free time, I usually read books 📘, play football ️⚽ and swimming  🏊. It helps me relax after a hard-working day 🥳🥳
      </p>
      <div class="hero__contact">
        <h3 class="hero__contact-heading txt__gradient-orange">Contact me at :</h3>
        <div class="hero__contact-list">
          <a class="btn__animate-01 hero__btn facebook" :href="contact.facebook" target="_blank" rel="noopener noreferrer">
            <span class="hero__btn-ico">
              <ion-icon name="logo-facebook"></ion-icon>
            </span>
            <span class="hero__btn-txt">Facebook</span>
          </a>
          <a class="btn__animate-01 hero__btn youtube" :href="contact.youtube" target="_blank" rel="noopener noreferrer">
            <span class="hero__btn-ico">
              <ion-icon name="logo-youtube"></ion-icon>
            </span>
            <span class="hero__btn-txt">Youtube</span>
          </a>
          <a class="btn__animate-01 hero__btn github" :href="contact.github" target="_blank" rel="noopener noreferrer">
            <span class="hero__btn-ico">
              <ion-icon name="logo-github"></ion-icon>
            </span>
            <span class="hero__btn-txt">Github</span>
          </a>
          <a class="btn__animate-01 hero__btn email" :href="contact.email" target="_blank" rel="noopener noreferrer">
            <span class="hero__btn-ico">
              <ion-icon name="mail"></ion-icon>
            </span>
            <span class="hero__btn-txt">Email</span>
          </a>
        </div>
      </div>
    </div>
    <div class="hero__img">
      <div class="hero__img-inner">
        <img src="/avatar.png" alt="">
      </div>
    </div>
  </section>
</template>
<script>

export default {
  name: "Hero",
  data() {
    return {
      contact: {
        facebook: "https://www.facebook.com/nvinhtieng/",
        youtube: "https://www.youtube.com/channel/UCV8NsXCp-h3-GNN0rQHeBeQ",
        github: "https://github.com/nguyenvinhtieng",
        email: "mailto:vinhtieng123@gmail.com?subject=Contact to Vinh Tieng&body=Hello! I visited your website and..."
      },
      name: "Nguyen Vinh Tieng",
      indexTitle: 0,
      styleTyping: true,
      firtsTime: true,
      lenghtJob: 1,
      jobIndex: 0,
      jobs: [
        {
          title: "Frontend Developer",
          status: true
        },
        {
          title: "Student",
          status: false
        }
      ]
    };
  },
  methods: {
    async changeJob() {
      let activeJob = this.jobs[this.jobIndex].title
      if(this.indexTitle < activeJob.length && this.styleTyping) {
        this.jobEl.innerHTML += activeJob[this.indexTitle]
        this.indexTitle += 1;
        this.firtsTime = false
      }
      else if(!this.styleTyping){
        this.jobEl.innerHTML = this.jobEl.innerHTML.slice(0, -1);
        this.indexTitle -= 1;
      }
      else if(this.indexTitle == activeJob.length){
        this.styleTyping = false;
      }
      if(this.indexTitle == 0 && !this.firtsTime) {
        this.styleTyping = true;
        if(this.jobIndex == this.lenghtJob){
          this.jobIndex = 0;
        }else{
          this.jobIndex += 1;
        }
      }
      setTimeout(this.changeJob, 200)
    }
  },
  mounted() {
    this.jobEl = this.$refs.job;
    this.jobEl.innerHTML = "";
    this.changeJob();
  },
};
</script>
<style>
  @import "../assets/styles/_hero.scss";
</style>