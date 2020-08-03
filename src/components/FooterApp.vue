<template>
  <div>
    <v-app id="inspire">
      <v-footer color="cyan darken-3" app>
        <span class="white--text">&copy; WgetDc {{ new Date().getFullYear() }}</span>
      </v-footer>
    </v-app>
  </div>
</template>

<script>
export default {
  props: {
    source: String,
  },
  data: () => ({
    drawer: null,
  }),
};
</script>

<style>
</style>