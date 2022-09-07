<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <ElButton type="primary">這是一個按鈕</ElButton>
  <el-button type="primary">這是一個按鈕</el-button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    console.log('process.env.VUE_APP_APIURL', process.env.VUE_APP_APIURL)

    this.$http.get(process.env.VUE_APP_APIURL).then((response) => {
      console.log(response.data)
    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
