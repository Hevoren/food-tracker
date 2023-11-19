<script>
import ProductPage from "@/components/Main/ProductPage.vue";
import AddProduct from "@/components/Main/AddProduct.vue";

export default {
  name: "ProductsPage",
  components: {
    ProductPage,
    AddProduct
  },
  data() {
    return {
      formVisible: false
    }
  },
  methods: {
    addProduct() {
      if (this.formVisible === false) {
        this.formVisible = true
      }
    },
  },
  mounted() {
    this.emitter.on('formVisible', isOpen => {
      this.formVisible = isOpen
    })
  }
}
</script>

<template>
  <div class="products">
    <div class="wrapper-products">
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
      <ProductPage/>
    </div>
    <div class="add-product-button">
      <button @click="addProduct">
        Добавить продукт
      </button>
    </div>
  </div>
  <div v-if="formVisible">
    <AddProduct :formVisible="formVisible"/>
  </div>
</template>

<style scoped>
.wrapper-products {
  display: grid;
  align-items: center;
  grid-template-columns: 250px 250px 250px 250px 250px 250px;
  grid-template-rows: 285px 285px;
}

.products {
  display: flex;
  flex-direction: column;
}

.add-product-button {
  margin-top: 20px;
  display: flex;
  justify-content: center;
}

.add-product-button button {
  font-size: 25px;
  color: white;
  background: none;
  border: none;
  transition: .3s ease-out;
}

button:hover {
  cursor: pointer;
  color: #851818;
}

</style>