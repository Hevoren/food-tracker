<script>
import ProductsPage from "@/components/Main/ProductsPage.vue";
export default {
  name: 'MainPage',
  components: {
    ProductsPage
  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <div>
    <ProductsPage/>
  </div>
</template>

<style scoped>
div {
  display: flex;
  justify-content: center;
}
</style>