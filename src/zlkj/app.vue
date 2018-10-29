<template lang="pug">
    #app {{msg}}
      input(type='text' v-model="msg")
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

    img {
      width: 100%;
      height: 300px;
    }
  }
</style>
