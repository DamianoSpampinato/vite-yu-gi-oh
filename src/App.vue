<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue'



export default {
  components: {
    AppHeader,
    CardsList

  },
  data() {
    return {
      store,
      QParams: {
        num: 20,
        offset:0,
      }
    };
  },
  methods: {
    getCardsFromApi() {

      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php',{
        params: this.QParams
      })
      .then((response) => {
        store.cardsArray= response.data.data;
        console.log(store.card)
      
      });
    }
  },
  mounted() {
  this.getCardsFromApi()
  }
}
</script>

<template>

<AppHeader></AppHeader>
<CardsList></CardsList>
</template>

<style lang="scss">
@use './style/generic';
</style>
