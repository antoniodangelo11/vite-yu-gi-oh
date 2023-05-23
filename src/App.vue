<script>
import AppTitle from './components/AppTitle.vue';
import FilterCards from './components/FilterCards.vue';
import FilterResults from './components/FilterResults.vue';
import CardsList from './components/CardsList.vue';
import axios from 'axios';
import { store } from './store';

export default {
  data() {
    return {
      store,
    };
  },

  components: {
    AppTitle,
    FilterCards,
    FilterResults,
    CardsList,
  },

  methods: {
    loadPage() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0',)
        .then(response => (this.store.CardsList = response.data.data));
    },

    requestDataFromApi() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/archetypes.php',)
        .then(response => (this.store.ArrArchetypes = response.data));
    },

    apiFilter() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
          params: {
            archetype: this.store.SearchArchetypes,
          }
        })
        .then(response => (this.store.CardsList = response.data.data));
    },
  },

  created() {
    setInterval(() => {
      this.loadPage();
      this.requestDataFromApi();
    }, 2000);
  },
};
</script>

<template>
  <header>
    <AppTitle />
  </header>

  <main>
    <FilterCards @performSearch="apiFilter" />
    <FilterResults />
    <CardsList />
  </main>
</template>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";

main {
  background-color: #D48F38;
  padding-bottom: 5rem;
}
</style>