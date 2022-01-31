<template>
  <div id="app">
      <Header />
      <MainContainer :dischi="dischi" />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import MainContainer from '@/components/MainContainer.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    MainContainer
  },
  data() {
    return {
      dischi: []
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.dischi = response.data.response
      // console.log(response.data.response)
    })
  },
}
</script>

<style lang="scss">
@import './style/main.scss';
@import './style/variables.scss';
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700&display=swap');
</style>
