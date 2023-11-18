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
    <div class="wrapper">
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
    <div class="add-product">
      <button @click="addProduct">
        Add Product
      </button>
    </div>
  </div>
  <div>
    <AddProduct :property="formVisible" v-show="formVisible"/>
  </div>
</template>

<style scoped>
.wrapper {
  display: grid;
  align-items: center;
  grid-template-columns: 250px 250px 250px 250px 250px 250px;
  grid-template-rows: 285px 285px;
}

.products {
  display: flex;
  flex-direction: column;
}

.add-product {
  margin-top: 20px;
  display: flex;
  justify-content: center;
}

.add-product button {
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


.product-form-background {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  display: table;
  transition: opacity 0.3s ease;
}
</style>