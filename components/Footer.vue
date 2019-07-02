<template>
  <footer>
    <ul>
      <li>
        <a
          rel="noopener noreferrer"
          target="_blank"
          href="mailto:contact@coppercup.nl"
          >contact@coppercup.nl</a
        >
      </li>
    </ul>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/scss/settings.scss";
@import "../assets/scss/mixins.scss";

footer {
  background: $white;
  color: $black;
  text-align: center;
  padding: $space-2 $space $space;

  li {
    padding: 0 1em;
  }

  li:not(:last-child) {
    margin-bottom: 1em;
  }

  a {
    @include stretchline($color: $black);
  }
}

@include media($screen-bronn) {
  footer ul {
    display: flex;
    justify-content: center;
  }
}
</style>
