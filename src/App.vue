<template>
  <AppHeader />
  <SelectComponent @selectedInput="getResponse()" />
  <CounterComponent />
  <AppMain />
</template>
<script>
import { store } from './store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CounterComponent from './components/CounterComponent.vue'
import SelectComponent from './components/SelectComponent.vue';
import AppMain from './components/MainContent/AppMain.vue';
export default {
  components: {
    AppHeader,
    CounterComponent,
    SelectComponent,
    AppMain
  },
  data() {
    return {
      store,
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?",
    }
  },
  methods: {
    getCards(archetypeInput = 'chaos') {
      axios.get(this.apiUrl, {
        params: {
          num: 20,
          offset: 0,
          archetype: archetypeInput,
          type: 'Effect Monster'

        }
      })
        .then((response) => {
          this.store.cardsList = (response.data.data);

        })
        .catch(function (error) {
          // handle error
          console.error(error);
        })
    },
    getResponse() {
      console.log('Connessione eseguita')
    }
  },
  created() {
    this.getCards();
  }
}
</script>
<style lang="scss">
@use './styles/partials/variables.scss' as *;
@use './styles/general.scss' as *;
@use 'bootstrap/scss/bootstrap.scss' as *;
</style>