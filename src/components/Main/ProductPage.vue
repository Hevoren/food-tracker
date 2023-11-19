<script>
export default {
  name: 'ProductPage'
}
</script>

<template>
<div>
  <div class="product">
    <div class="product-item">
      <h1>Название</h1>
      <p>Каллорийность</p>
      <p>Вес</p>
      <p>Белки</p>
      <p>Жиры</p>
      <p>Углеводы</p>
    </div>
  </div>
</div>
</template>

<style scoped>
.product {
  background-color: #851818;
  height: 250px;
  width: 200px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.product-item {
  background-color: #851818;
}

.product-item > p {
  background-color: #851818;
  margin-left: 15px;
  color: white;
  font-size: 14px;
}

h1 {
  background-color: #851818;
  margin-left: 15px;
  color: white;
}
</style>