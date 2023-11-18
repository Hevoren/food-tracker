<script>
import Search from "@/components/Search.vue";

export default {
  name: 'HeaderPage',
  components: {
    Search
  }
}
</script>

<template>
  <div class="header">
    <div class="menu">
      <a href="#">Products</a>
      <a href="#">Days</a>
    </div>
    <div>
      <Search/>
    </div>
  </div>

</template>

<style scoped>
  .header {
    display: flex;
    flex-direction: row;
    text-align: center;
    justify-content: center;
    align-items: center;
  }

  .menu {
    display: flex;
    flex-direction: row;
  }

  .menu > a {
    color: white;
    font-size: 25px;
    outline: none;
    text-decoration: none;
    padding: 25px;
    transition: .4s ease-in-out;
  }

  a:hover {
    transition: .4s ease-out;
    color: red;
  }
</style>