<template>
  <HeaderPage/>
  <MainPage/>
</template>

<script>
import HeaderPage from "@/components/HeaderPage.vue";
import MainPage from "@/components/MainPage.vue";

export default {
  name: 'App',
  components: {
    MainPage,
    HeaderPage
  }
}
</script>

<style scoped>
.search {
  margin-top: 50px;
}
</style>
