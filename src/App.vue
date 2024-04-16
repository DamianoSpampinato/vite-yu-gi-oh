<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import Loader from './components/Loader.vue';
import Search from './components/Search.vue'



export default {
  components: {
    AppHeader,
    CardsList,
    Loader,
    Search

  },
  data() {
    return {
      store,
     
    };
  },
  methods: {
    getCardsFromApi() {
      const QParams = {
        num: 20,
        offset:0,
      }
      if(store.searchedArchetype !== '') {
     QParams.archetype = store.searchedArchetype;
    }
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php',{
        params: QParams
      })
      .then((response) => { 
        store.cardsArray= response.data.data;
        store.isLoading = false;
      
      });
    },
    getArchetypes(){
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then((response) => {
        store.archetypes = response.data;
      })
    }
  },
  mounted() {
  this.getCardsFromApi()
  this.getArchetypes()
  }
}
</script>

<template>

<AppHeader></AppHeader>
<CardsList v-if="!store.isLoading"></CardsList>
<Loader v-else></Loader>
<Search @searchPerformed="getCardsFromApi"></Search>
</template>

<style lang="scss">
@use './style/generic';
</style>
