<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

@keyframes slideUpAnimation {
  from {
    margin-top: 500px;
  }
  to {
    margin-top: 0px;
  }
}

@keyframes slideInLeftAnimation {
  from {
    margin-left: 500px;
  }
  to {
    margin-left: 0px;
  }
}

.slideUp {
  animation-name: slideUpAnimation;
  animation-duration: 0.9s;
}
.slideInLeft {
  animation-name: slideInLeftAnimation;
  animation-duration: 0.9s;
}
</style>
