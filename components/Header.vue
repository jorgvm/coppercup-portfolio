<template>
  <header>
    <h1>
      <img class="banner" alt="" :src="headerImage" /><span>Copper Cup</span>
    </h1>
  </header>
</template>

<script>
import headerImage from "../assets/images/header.jpg";

export default {
  data() {
    return {
      headerImage
    };
  }
};
</script>

<style lang="scss" scoped>
.banner {
  width: 100%;
}

span {
  text-indent: -9999px;
  display: block;
}

h1 {
  margin-bottom: 0;
}
</style>
