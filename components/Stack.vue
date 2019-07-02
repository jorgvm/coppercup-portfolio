<template>
  <section class="stack">
    <div class="wrap">
      <i class="fa fa-gears" aria-hidden="true"></i>
      <p class="tools">
        <strong>Vue</strong>, <strong>React</strong>, Javascript
        (<strong>ES6</strong>), <br />
        CSS3 (<strong>SCSS</strong>), Photoshop,Sketch<br />
        <strong>Git</strong>, Jira
      </p>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/scss/settings.scss";

.stack {
  padding: 4rem $space;

  .wrap {
    max-width: 440px;
  }

  .tools {
    font-family: $font-family-alt;
    font-size: 1.5em;
  }

  .fa {
    font-size: 28px;
    margin-bottom: 1em;
  }
}
</style>
