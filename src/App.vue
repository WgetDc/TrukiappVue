<template>
  <div>
    <content-app />
    <AppBar />
    <side-menu />
    <footer-app />
  </div>
</template>

<script>
import AppBar from "./components/AppBar.vue";
import ContentApp from "./components/ContentApp.vue";
import FooterApp from "./components/FooterApp.vue";

export default {
  name: "App",
  components: {
    AppBar,
    ContentApp,
    FooterApp,
  },
};
</script>

<style>
</style>
