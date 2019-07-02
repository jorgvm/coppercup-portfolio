<template>
  <div class="inner">
    <div class="project-image"><img :src="projectImage" alt="" /></div>
    <div class="project-info">
      <h3>Github</h3>

      <p>
        Voor meer demo's:<br />

        <IconCode class="icon" decorative :size="20" />
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://github.com/jorgvm/"
        >
          Repositories op Github
        </a>
      </p>

      <p>
        <strong>Benieuwd naar mijn vorige klussen?</strong><br />
        Lees meer informatie op
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://www.linkedin.com/in/jorgvanmaaren"
          >LinkedIn</a
        >

        of neem contact met mij op via
        <a
          class="no-icon"
          rel="noopener noreferrer"
          target="_blank"
          href="mailto:contact@coppercup.nl"
        >
          <i class="fa fa-envelope" aria-hidden="true"></i>
          contact@coppercup.nl
        </a>
      </p>
    </div>
  </div>
</template>

<script>
import projectImage from "../../assets/images/project-github.png";
import IconCode from "vue-material-design-icons/IframeOutline.vue";
import IconDemo from "vue-material-design-icons/GamepadVariantOutline.vue";

export default {
  components: {
    IconCode,
    IconDemo
  },
  data() {
    return {
      projectImage
    };
  }
};
</script>
