 <template>
  <div class="social-wrap">
    <ul>
      <li>
        <a :href="links.facebook" target="_blank">
          <font-awesome-icon class="icon" :icon="['fab', 'facebook-square']" />
        </a>
      </li>
      <li>
        <a :href="links.instagram" target="_blank">
          <font-awesome-icon class="icon" :icon="['fab', 'instagram-square']" />
        </a>
      </li>
      <li>
        <a :href="links.linkedin" target="_blank">
          <font-awesome-icon class="icon" :icon="['fab', 'linkedin']" />
        </a>
      </li>
      <li>
        <a :href="links.github" target="_blank">
          <font-awesome-icon class="icon" :icon="['fab', 'github-square']" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SocialBar",
  props: ["links"],
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";
.social-wrap {
  li {
    display: inline-block;
    margin-right: 10px;
  }
  .icon {
    font-size: 3rem;
  }
}
</style>
