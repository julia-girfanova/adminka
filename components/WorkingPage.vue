<template>
  <div class="page">
    <PageHeader />
    <SuperWorkingPage />
  </div>
</template>

<script>
import PageHeader from "../components/PageHeader.vue";
import SuperWorkingPage from "../components/SuperWorkingPage.vue";
export default {
  components: {
    PageHeader,
    SuperWorkingPage,
  },
};
</script>

<style>
.page {
  display: flex;
  flex-direction: column;
  width: 100%;
  width: calc(100% - 250px);
  margin-left: 250px;
}
</style>
