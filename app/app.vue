<template>
  <div class="app">
    <Sidebar />
    <WorkingPage />
  </div>
</template>
<script>
import Sidebar from "../components/Sidebar.vue";
import WorkingPage from "../components/WorkingPage.vue";
export default {
  components: {
    Sidebar,
    WorkingPage,
  },
};
</script>
<style>
body {
  margin: 0px;
  font-family: sans-serif;
  min-height: 100vh;
  display: flex;
}
.app {
  height: 100%;
  display: flex;
}
#__nuxt {
  min-height: 100%;
  width: 100%;
}
</style>
