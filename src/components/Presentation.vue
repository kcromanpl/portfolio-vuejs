<template>
  <div class="paragraph">
    <h3>{{ content.pres_title }}</h3>
    <div class="begin">{{ content.pres_first }}</div>
    <p class="pres-second">{{ content.pres_second }}</p>
  </div>
</template>

<script>
export default {
  name: "Description",
  props: ["content"],
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

.paragraph {
  color: map-get($colors, primary);

  .begin {
    color: map-get($colors, secondary);
  }

  .pres-second {
    margin-top: 10px;
  }
}
</style>
