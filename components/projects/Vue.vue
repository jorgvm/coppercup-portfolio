<template>
  <div class="inner">
    <div class="project-image"><img :src="projectImage" alt="" /></div>
    <div class="project-info">
      <h3>Vue</h3>

      <p>
        Deze portfolio site, omgezet naar Vue:<br />

        <IconCode class="icon" decorative :size="20" />
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://github.com/jorgvm/coppercup-portfolio"
        >
          Code op Github
        </a>
      </p>

      <p>
        <strong>Persgroep</strong><br />
        Voor de Persgroep heb ik in aan
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://volkskrant.nl/abonneren"
          >krant.nl</a
        >
        gewerkt, de website waar gebruikers zich kunnen abonneren voor o.a. de
        Volkskrant, Trouw en het AD. <br />
        De code is uiteraard niet openbaar, ik kan hier in een kennismaking
        gesprek meer over vertellen.
      </p>
    </div>
  </div>
</template>

<script>
import projectImage from "../../assets/images/project-vue.jpg";
import IconCode from "vue-material-design-icons/IframeOutline.vue";
export default {
  components: {
    IconCode
  },
  data() {
    return {
      projectImage
    };
  }
};
</script>
