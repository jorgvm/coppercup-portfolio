<template>
  <section class="projects">
    <div class="inner">
      <div class="gallery">
        <button
          v-for="project in allowedProjects"
          @click.prevent="selectProject(project)"
        >
          <component
            v-if="project.icon"
            :is="project.icon"
            :size="30"
            decorative
            title=""
          />
          {{ project.title }}
        </button>
      </div>

      <ProjectDetail v-if="projectComponent" @close="closeProject">
        <component :is="projectComponent" />
      </ProjectDetail>
    </div>
  </section>
</template>

<script>
import IconReact from "vue-material-design-icons/React.vue";
import IconVue from "vue-material-design-icons/Vuejs.vue";
import IconGithub from "vue-material-design-icons/GithubCircle.vue";

import ProjectDetail from "./ProjectDetail";
const projects = require.context("./projects/");

export default {
  components: {
    ProjectDetail,
    IconReact,
    IconVue,
    IconGithub
  },
  data() {
    return {
      activeProject: null,
      allowedProjects: [
        { file: "React", title: "React", icon: "IconReact" },
        { file: "Vue", title: "Vue", icon: "IconVue" },
        { file: "Github", title: "Github", icon: "IconGithub" }
      ]
    };
  },
  methods: {
    selectProject(project) {
      this.activeProject = project.file;
    },

    closeProject() {
      this.activeProject = null;
    }
  },
  computed: {
    projectComponent() {
      if (
        this.activeProject &&
        projects.keys().includes(`./${this.activeProject}`)
      ) {
        return projects(`./${this.activeProject}`).default;
      } else {
        return null;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/settings.scss";
@import "../assets/scss/mixins.scss";

// wrapper
.projects {
  background: $white;
  color: $black;
  padding: $space;
}

.inner {
  position: relative;
  overflow: hidden;
}

// List
.gallery {
  display: flex;
  justify-content: center;
  flex-direction: column;
  transition: all 2s;

  button {
    flex: 0 1 auto;
    width: 100%;
    transition: all 0.3s ease-in-out;
    position: relative;
    padding: 0.7em;
    margin: 0.2em 0;
    background: black;
    color: white;
    font-family: $font-family-alt;
    font-weight: bold;
    font-size: 1.7em;
    background: #d37b8a;
  }

  button:nth-child(2) {
    background: #f69957;
  }

  button:nth-child(3) {
    background: #f65772;
  }

  button:hover {
    transform: scale(1.1);
  }
}

/* Medium and larger screens */
@include media($screen-bronn) {
  .gallery {
    min-height: 440px;
  }

  .gallery button {
    font-size: 2.5em;
  }
}
</style>
