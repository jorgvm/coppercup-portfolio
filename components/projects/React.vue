<template>
  <div class="inner">
    <div class="project-image"><img :src="projectImage" alt="" /></div>
    <div class="project-info">
      <h3>React</h3>

      <p>
        <strong>Hacker News feed</strong><br />
        <em>React, MobX, Babel proposals, Hacker News API</em><br /><br />
        <IconDemo class="icon" decorative :size="20" />
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://coppercup-hackernews.netlify.com/"
        >
          Demo op Netlify
        </a>
        <br />
        <IconCode class="icon" decorative :size="20" />
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://github.com/jorgvm/hacker-news"
        >
          Git repository
        </a>
      </p>

      <p>
        <strong>"Movie Madness" app</strong><br />
        <em>React, 3rd party API's, Styled Components, Firebase</em><br /><br />
        <IconDemo class="icon" decorative :size="20" />
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="http://movie-madness-tm.firebaseapp.com"
        >
          Demo op Firebase
        </a>
        <br />
        <IconCode class="icon" decorative :size="20" />
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://github.com/jorgvm/movie-madness"
        >
          Git repository
        </a>
      </p>
    </div>
  </div>
</template>

<script>
import IconCode from "vue-material-design-icons/IframeOutline.vue";
import IconDemo from "vue-material-design-icons/GamepadVariantOutline.vue";
import projectImage from "../../assets/images/project-react.jpg";

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
