<template>
  <div class="about">
    <h1 class="slideUp">Stay in touch for more intresting stuff</h1>
    <a href="http://facebook.com/aenumair">
      <img class="image" src="../assets/facebook.jpg"
    /></a>
    <a href="https://github.com/UmairMukhtar">
      <img class="image slideUp" src="../assets/github.jpg"
    /></a>
    <a href="https://pk.linkedin.com/in/umair-mukhtar-828510153">
      <img class="image slideUp" src="../assets/linkedin.jpg"
    /></a>
    <a href="https://twitter.com/aenumair">
      <img class="image" src="../assets/twitter.jpg"
    /></a>
  </div>
</template>
<style scoped>
@keyframes sideBarSlide {
  from {
    margin-top: 500px;
  }
  to {
    margin-top: 0px;
  }
}
.image {
  width: 150px;
  height: 150px;
  border-radius: 25;
}
.heading {
  animation-name: sideBarSlide;
  animation-duration: 0.6s;
}
.container {
  height: 20px;
  flex: 6;
}
</style>
