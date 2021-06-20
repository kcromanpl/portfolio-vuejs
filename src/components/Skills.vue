<template>
  <section id="skills">
    <AnimateOnVisible name="fadeDown" :duration="1">
      <Title :title="content.title" :description="content.description" />
    </AnimateOnVisible>

    <div class="section-content">
      <div class="container-fluid">
        <div class="row d-flex flex-wrap align-items-center">
          <div
            class="col-md-2 m-auto pb-4"
            v-for="(post, index) in this.content.items"
            :key="index"
          >
            <AnimateOnVisible name="bounce">
              <img
                id="imgLogo"
                class="img-responsive mx-auto d-block"
                :src="getImgUrl(post.img)"
                :alt="post.title"
              />
              <div id="divAlt" class="altCaption text-center">
                {{ post.title }}
              </div>
            </AnimateOnVisible>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Title from "./Title.vue";

export default {
  name: "Skills",
  components: {
    Title,
  },
  methods: {
    getImgUrl(img) {
      return require("../assets/img/logo/" + img);
    },
  },
  created() {
    this.content = {
      title: "SKILLS",
      description: "Stacks I've been working on",
      items: [
        { title: "Ruby", img: "ruby.png" },
        { title: "Rails", img: "rails.png" },
        { title: "Sinatra", img: "sinatra.png" },
        { title: "Python", img: "python.png" },
        { title: "HTML", img: "html.png" },
        { title: "CSS", img: "css.png" },
        { title: "JS", img: "js.png" },
        { title: "Angular", img: "angular.png" },
        { title: "VueJS", img: "vuejs.png" },
        { title: "React", img: "react.png" },
        { title: "C", img: "C.png" },
        { title: "C++", img: "cplusplus.png" },
        { title: "Linux", img: "linux.png" },
        { title: "Git/Github", img: "Octocat.png" },
        { title: "Docker", img: "docker.png" },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

#skills {
  background-color: lighten(map-get($colors, dark), 100%);
}

@media (min-width: #{map-get($breakpoints, medium)}) {
  .section-content {
    width: 80%;
    margin: 0 auto;
  }
}

img {
  max-width: 120px;
}

.altCaption {
  color: map-get($colors, secondary);
  margin-top: 1rem;
}
</style>
