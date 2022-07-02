<template>
  <div class="search">
    <h2 class="title">Search Github Users</h2>
    <div class="inp">
      <input type="text" placeholder="enter the name you search" v-model="keyWord">
      <button class="btn" @click="searchUsers">Search</button>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'
  export default {
    name: 'Search',
    data() {
      return {
        keyWord: ''
      }
    },
    methods: {
      searchUsers() {
        // 请求前更新数据
        this.$bus.$emit('getUsers', {
          isFirst: false,
          isLoading: true,
          // errMsg: '',
          users: []
        })
        axios.get(`https://api.github.com/search/users?q=${this.keyWord}`).then(
          response => {
            // console.log('请求成功了', response.data)
            // 请求成功后更新数据
            this.$bus.$emit('getUsers', {
              // isFirst: false,
              isLoading: false,
              // errMsg: '',
              users: response.data.items
            })
          },
          error => {
            // console.log('请求失败了', error.message)
            // 请求失败后更新数据
            this.$bus.$emit('getUsers', {
              // isFirst: false,
              isLoading: false,
              errMsg: error.message,
              users: []
            })
          }
        )
      }
    }
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