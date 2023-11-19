<script>
export default {
  name: 'AddProduct',
  methods: {
    closeForm() {
      this.emitter.emit('formVisible', false)
    }
  },
  props: {
    formVisible: {
      type: Boolean,
      required: true
    }
  }
}
</script>

<template>
  <div @click="closeForm" :class="{ 'form-product-bg': formVisible }">
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
  background: none;
  outline: none;
  border: none;
  border-bottom: 1px solid black;
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