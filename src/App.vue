<template>
  <transition name="fade" tag="div" class="wrapper" mode="out-in">
    <div class="wrapper" v-if="isLoaded" id="app">
      <LandingPage :user="user" />
      <Description :user="user" :links="links" />
      <Experience />
      <Skills />
      <!-- <Projects :content="findSlug('projects')" /> -->
      <Footer :user="user" :links="links" />
    </div>
  </transition>
</template>

<script>
import LandingPage from "./components/LandingPage.vue";
import Description from "./components/Description.vue";
import Experience from "./components/Experience.vue";
import Skills from "./components/Skills.vue";
// import Projects from "./components/Projects.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    LandingPage,
    Description,
    Experience,
    Skills,
    // Projects,
    Footer,
  },
  data: () => ({
    isLoaded: false,
    user: {},
    posts: [],
  }),
  created() {
    document.body.classList.add("loading");

    this.user = {
      name: "Roman KC",
      status: "Full-Stack Developer",
      email: "kcromanpl@gmail.com",
      phone: "+977 - 9843267195",
      city: "Lalitpur",
      lang: "English, Nepali, Hindi",
      photo: "photo.png",
    };

    this.links = {
      facebook: "https://www.facebook.com/kcromanpl/",
      instagram: "https://www.instagram.com/kcromanpl/",
      linkedin: "https://www.linkedin.com/in/kcromanpl/",
      github: "https://github.com/kcromanpl",
    };

    this.isLoaded = true;
    this.$nextTick(() => document.body.classList.remove("loading"));
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

#app {
  font-family: Montserrat-Regular, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.wrapper {
  height: 100%;
}
</style>
