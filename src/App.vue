<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from './views/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
.no-wrap {
  white-space: nowrap;
}
@font-face {
  font-family: "Lato";
  src: url(./fonts/Lato/Lato-Regular.ttf);
}
@font-face {
  font-family: "Impact";
  src: url(./fonts/Impact/impact.ttf);
}
#app {
  font-family: "Lato", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
  width: 100vw;
  max-width: 100vw;
  overflow-x: hidden;
}
h1, h2, h3, h4 {
  font-family: "Impact";
  letter-spacing: 2px;
}
html, body {
  margin: 0;
  width: 100vw;
  overflow-x: hidden;
  scroll-behavior: smooth;
}
@media (max-width: 500px) {
  h1, h2, h3, h4 {
    letter-spacing: 1px;
  }
}
</style>
