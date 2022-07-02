<template>
  <div class="list">
    <div class="item">
      <div class="img">
        <img src="../assets/logo.png" alt="">
      </div>
      <span class="name">vue_test</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'List'
  }
</script>

<style scoped>
  .list {
    width: 100%;
    overflow: hidden;
  }

  .list > .item {
    float: left;
    height: 300px;
    width: 300px;
    /* border: 1px solid #333; */
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
  }

  .item > .img {
    width: 200px;
    height: 200px;
  }

</style>