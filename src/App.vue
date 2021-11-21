<template>
  <div id="app">
    <Dashboards :api="url" />
  </div>
</template>

<script>
const apiUrl = process.env.VUE_APP_API_URL;

export default {
  name: 'App',

  data() {
    return {
      url: apiUrl || 'http://localhost:8083',
    };
  },
};
</script>

<style lang="stylus">
@import "~/src/_stylebase.styl";
</style>
