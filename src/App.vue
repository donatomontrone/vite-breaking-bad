<template>
  <AppHeader />
  <CounterComponent />
  <AppMain />
</template>
<script>
import { store } from './store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/MainContent/AppMain.vue';
import CounterComponent from './components/CounterComponent.vue'
export default {
  components: {
    AppHeader,
    CounterComponent,
    AppMain,
  },
  data() {
    return {
      store,
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=1627",
    }
  },
  methods: {
    getCard() {
      axios.get(this.apiUrl, {
        params: {
        }
      })
        .then((response) => {
          this.store.cardsList = (response.data.data);

        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
    }
  },
  created() {
    this.getCard();
  }
}
</script>
<style lang="scss">
@use './styles/partials/variables.scss' as *;
@use './styles/general.scss' as *;
@use 'bootstrap/scss/bootstrap.scss' as *;
</style>