<script>
export default {
  name: 'ProductPage',
}
</script>

<template>
<div>
  <div class="product">
    <div class="product-item">
      <h1>Title</h1>
      <p>Kcal</p>
      <p>Weight</p>
      <p>Protein</p>
      <p>Fats</p>
      <p>Carbohydrates</p>
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