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
        <input type="text" name="input" placeholder="Название">
        <input type="text" name="kcal" placeholder="Каллорийность">
        <input type="text" name="weight" placeholder="Вес">
        <input type="text" name="protein" placeholder="Белки">
        <input type="text" name="fats" placeholder="Жиры">
        <input type="text" name="carbohydrates" placeholder="Углеводы">
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
  opacity: 0.5;
  font-weight: normal;
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