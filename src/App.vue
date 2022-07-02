<template>
  <div class="container">
    <Search/>
    <List/>
  </div>
</template>

<script>
  import Search from './components/Search'
  import List from './components/List'

  export default {
    name: 'App',
    components: {
      Search,
      List
    }
  }
</script>

<style>
  * {
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .container {
    width: 900px;
    /* border: 1px solid #333; */
    margin: 10px auto;
  }

  img {
    width: 100%;
    height: 100%;
  }
</style>
