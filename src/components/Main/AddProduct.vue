<script>
import { setItem, getItem } from "@/helpers/persistanceStorage";

export default {
  name: 'AddProduct',
  props: {
    formVisible: {
      type: Boolean,
          required: true
    }
  },
  data() {
    return {
      products: {
        title: '',
        kcal: '',
        weight: '',
        proteins: '',
        fats: '',
        carbohydrates: '',
      }
    }
  },
  methods: {
    closeForm() {
      this.emitter.emit('formVisible', false)
    },
    onSubmit() {
      this.products = {
        title: '',
        kcal: '',
        weight: '',
        proteins: '',
        fats: '',
        carbohydrates: '',
      };
      this.closeForm()
    },
    saveProductToLocalStorage() {
      setItem('products', JSON.stringify(this.products))
    }
  },
  watch: {
    products: {
      handler: 'saveProductToLocalStorage',
      deep: true
    }
  },
  mounted() {
    if (getItem('products')) {
      this.products = JSON.parse(getItem('products'))
    }
  }
}
</script>

<template>
  <div @click="closeForm" :class="{ 'form-product-bg': this.formVisible }">
    <div class="form-product" @click.stop>
      <form action="/" @submit.prevent="onSubmit">
        <input type="text" name="input" placeholder="Название" v-model="products.title">
        <input type="text" name="kcal" placeholder="Каллорийность" v-model="products.kcal">
        <input type="text" name="weight" placeholder="Вес" v-model="products.weight">
        <input type="text" name="protein" placeholder="Белки" v-model="products.proteins">
        <input type="text" name="fats" placeholder="Жиры" v-model="products.fats">
        <input type="text" name="carbohydrates" placeholder="Углеводы" v-model="products.carbohydrates">
        <button type="submit">Add</button>
      </form>
    </div>
  </div>
</template>

<style scoped>

.form-product {
  display: flex;
  width: 400px;
  height: 500px;
}

form {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
  background-color: #851818;
  border-radius: 15px;
}

.form-product input {
  color: black;
  font-size: 16px;
  background: none;
  outline: none;
  border: none;
  height: 60px;
  width: 80%;
  border-bottom: 1px solid black;
  font-weight: bold;
}

.form-product button {
  height: 40px;
  width: 80%;
  background-color: black;
  border: none;
  border-radius: 15px;
  margin-top: 20px;
  color: white;
  font-size: 20px;
  transition: .8s ease;
}

.form-product button:hover {
  transition: .8s ease;
  background-color: white;
  color: black;
  cursor: pointer;
}

.form-product input::placeholder {
  color: black;
  font-weight: bold;
}

.form-product-bg {
  z-index: 1;
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
}


</style>