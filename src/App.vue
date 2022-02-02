<template>
  <div id="app">
      <Header />
      <SelectOptions @filter="doFilter"/>
      <MainContainer :dischi="dischiFiltered" />
      <!-- CON LOADER: v-else and v-if per attivare il loader, sennò non li scrivo -->
      <!-- <LoaderComponent v-if="!flagLoaded" />
      <MainContainer v-else :dischi="dischiFiltered"/> -->
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import SelectOptions from '@/components/SelectOptions.vue'
// import LoaderComponent from '@/components/LoaderComponent.vue'
import MainContainer from '@/components/MainContainer.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    SelectOptions,
    // LoaderComponent,
    MainContainer,
  },
  data() {
    return {
      dischi: [],
      dischiFiltered: [], //secondo array dentro cui ci saranno gli album filtrati e verranno stampati in pagina
      // flagLoaded: false, // setTimeout
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.dischi = response.data.response; // console.log(response.data.response)
      this.dischiFiltered = response.data.response;  //in questo modo andiamo a dire che l'array filtrato inizialmente deve essere uguale al response che arriva da data

      // setTimeout(() => { // setTimeout per visualizzare il loader, ritardando la creazione e la stampa degli album in pagina
      //   axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      //   this.dischi = response.data.response;
      //   this.dischiFiltered == response.data.response;
      //   this.flagLoaded = true; //per visualizzare il loader prima che vengano stampati gli elementi del data 
      // });
      // }, 1000);
    });
  },
  methods: {
    doFilter(genre) {
      this.dischiFiltered = this.dischi.filter((disco) => {
        return disco.genre.toLowerCase() === genre || genre ==="all";
      })
    }
  },
}
</script>

<style lang="scss">
@import './style/main.scss';
@import './style/variables.scss';
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700&display=swap');
</style>