<template>
  <div>
    <Header />

    <main>
      <Intro />
      <Projects />
      <Stack />
    </main>

    <Footer />
  </div>
</template>

<script>
import Header from "../components/Header";
import Intro from "../components/Intro";
import Projects from "../components/Projects";
import Stack from "../components/Stack";
import Footer from "../components/Footer";

export default {
  components: {
    Header,
    Intro,
    Projects,
    Stack,
    Footer
  }
};
</script>

<style lang="scss">
@import "../assets/scss/reset.scss";
@import "../assets/scss/settings.scss";
@import "../assets/scss/mixins.scss";
@import "../assets/scss/base.scss";

main {
  margin: 0 auto;
  text-align: center;
}
</style>
