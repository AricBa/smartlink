<template lang="pug">
    h1 {{msg}}
      //- img(src="./assets/imgs/logo.jpeg")
      //- input(type='text' v-model="msg")
</template>

<script>
  import getData from './util/utils'

  export default {
    name: 'app',
    data() {
      return {
        msg: 'Welcome to Your Vue.js'
      }
    },
    created() {
      this.fetchData()
    },
    methods: {
      async fetchData() {
        const data = await getData()
        this.msg = data
      }
    }
  }
</script>

<style lang="scss" scoped>
  #app {
    font-family: Arial, Helvetica, sans-serif;

    h1 {
      color: green;
    }
  }
</style>
