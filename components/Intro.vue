<template>
  <section class="intro">
    <div class="wrap">
      <h2>
        Front-end web developer
      </h2>

      <div class="avatar">
        <img alt="Jorg van Maaren" :src="avatarImage" />
      </div>

      <p>
        Jorg van Maaren
      </p>

      <p>
        Ik denk graag mee over het ontwerp en de gebruiksvriendelijkheid van het
        product - zorgen dat een website er strak uitziet en meedenken met alle
        onderdelen waar de eindgebruiker mee in aanraking komt.
      </p>

      <p class="moreinfo">
        Lees meer informatie op
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://www.linkedin.com/in/jorgvanmaaren"
          >LinkedIn</a
        >,
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="https://github.com/jorgvm/"
          >Github</a
        >
        <br />
        of
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="mailto:contact@coppercup.nl"
          ><i class="fa fa-envelope" aria-hidden="true"></i> laat wat van je
          horen</a
        >
      </p>
    </div>
  </section>
</template>

<script>
import avatarImage from "../assets/images/jorg.jpg";

export default {
  data() {
    return {
      avatarImage
    };
  }
};
</script>

<style lang="scss" scoped>
@import "./../assets/scss/settings.scss";

.intro {
  padding: 0 0 $space-2;
  text-shadow: 1px 1px rgba($black, 0.1);
  position: relative;
  z-index: 1;

  .wrap {
    padding: 0 $space;
  }

  .highlight {
    border: 1px solid white;
    display: inline-block;
    padding: 20px;
    margin-top: 20px;
  }

  p {
    font-size: 1.1em;
  }

  .moreinfo {
    margin: $space-2 0;
  }

  .fa-envelope {
    font-size: 0.6em;
    position: relative;
    top: -2px;
    margin-left: 5px;
  }
}
</style>
