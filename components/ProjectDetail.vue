<template>
  <div class="detail" :class="[hidden ? 'hidden' : '']">
    <button @click.prevent="close()" aria-label="close" class="close">
      <IconClose title="close" :size="35" />
    </button>
    <slot />
  </div>
</template>

<script>
import VueTypes from "vue-types";
import IconClose from "vue-material-design-icons/Close.vue";

export default {
  data() {
    return {
      hidden: true,
      animationSpeed: 600
    };
  },
  components: {
    IconClose
  },
  methods: {
    listen(event) {
      // Listen for escape key
      if (event.keyCode == 27) {
        this.close();
      }
    },
    close() {
      this.hidden = true;
      setTimeout(() => {
        this.$emit("close");
      }, this.animationSpeed);
    }
  },
  mounted() {
    this.$nextTick(() => {
      setTimeout(() => {
        this.hidden = false;
      }, 100);
    });

    document.addEventListener("keydown", this.listen);
  },
  beforeDestroy() {
    document.removeEventListener("keydown", this.listen);
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/settings.scss";
@import "../assets/scss/mixins.scss";

// Detail
.detail {
  position: fixed;
  top: 0;
  left: 0;
  will-change: transform;
  width: 100%;
  height: 100%;
  z-index: 1;
  overflow-y: scroll;
  background: $white;
  text-align: left;
  transition: transform $speed $cubic-bezier;
  transform: translateY(0%);

  &.hidden {
    transform: translateY(-100%);
  }
}

.close {
  position: absolute;
  outline: none;
  display: inline-block;
  top: 0;
  right: 0;
  height: 35px;
  width: 37px;

  z-index: 1;

  color: $green;
  border-radius: 0 0 0 2px;
  background: $white;
  text-align: center;
  cursor: pointer;
  line-height: 1.6em;
  transition: transform $speed $cubic-bezier;
  transition-delay: 0.5s;

  &:active {
    color: red;
  }

  &:hover {
    transition-delay: 0;
    transform: rotate(180deg);
  }
}

/* Medium and larger screens */
@include media($screen-bronn) {
  .detail {
    position: absolute;
  }

  /* Detail close button, performance issues on mobile, only only bigger screens */
  .close {
    transform: translate(0, 0);
    transition: all $speed $cubic-bezier 0;
  }

  .detail.hidden .close {
    transform: translate(100%, 0);
  }
}
</style>

<!-- Deep styles -->
<style lang="scss" scoped>
@import "../assets/scss/settings.scss";
@import "../assets/scss/mixins.scss";

/deep/ .inner {
  a {
    @include stretchline(null, $black);
  }

  .icon {
    vertical-align: sub;
  }

  .project-image {
    display: block;
    overflow: hidden;
    max-height: 200px;

    img {
      width: 100%;
      margin-bottom: 1em;
    }
  }

  .project-info {
    padding: 2em 1em 1em;
    max-width: 600px;
    margin: 0 auto;
  }

  h3,
  .project--link {
    text-align: center;
  }

  .project--link {
    margin-top: 4em;
  }

  p:not(:last-child) {
    margin-bottom: 2em;
  }
}

/* Medium and larger screens */
@include media($screen-bronn) {
  /deep/ .inner {
    display: flex;
    align-items: center;
    overflow: hidden;
    padding: 0;

    .project-image {
      max-height: none;
    }

    .project-image img {
      margin: 0;
      max-width: 50vw;
      width: 100%;
    }
  }
}
</style>
