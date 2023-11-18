<script>
export default {
  name: 'AddProduct',
  data() {
    return {
      formVisible: true
    }
  },
  methods: {
    closeForm() {
      this.emitter.emit('formVisible', false)
    }
  }
}
</script>

<template>
  <div v-show="formVisible" @click="closeForm" class="form-product-bg">
    <div class="form-product" @click.stop>
      <form>
        <input type="text" name="input" value="Title">
        <input type="text" name="kcal" value="Kcal">
        <input type="text" name="weight" value="Weight">
        <input type="text" name="protein" value="Protein">
        <input type="text" name="fats" value="Fats">
        <input type="text" name="carbohydrates" value="Carbohydrates">
        <button type="submit">Add</button>
      </form>
    </div>
  </div>
</template>

<style scoped>
.form-product {
  z-index: 9999999;
  position: relative;
  display: flex;
  width: 400px;
  height: 500px;
}

form {
  display: flex;
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: #851818;
  border-radius: 15px;
}

.form-product input {
  background: none;
  outline: none;
  border: none;
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
  transition: opacity 0.3s ease;
  justify-content: center;
  align-items: center;
}

</style>