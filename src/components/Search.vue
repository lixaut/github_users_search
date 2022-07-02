<template>
  <div class="search">
    <h2 class="title">Search Github Users</h2>
    <div class="inp">
      <input type="text" placeholder="enter the name you search">
      <button class="btn">Search</button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Search'
  }
</script>

<style scoped>
  .search {
    width: 100%;
    height: 200px;
    background-color: #d4d4d4;
    /* margin-bottom: 20px; */
    border-radius: 5px;
  }

  .search > h2 {
    padding: 40px 0;
    text-align: center;
  }

  .search > .inp {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 16px;
    line-height: 30px;
  }

  .inp > .btn {
    height: 30px;
    width: 60px;
    border-radius: 5px;
  }

  .inp > input {
    height: 30px;
    width: 190px;
    outline: none;
    border: 1px solid #333;
    border-radius: 5px;
    margin-right: 5px;
  }
</style>