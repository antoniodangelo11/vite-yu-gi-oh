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
    requestDataFromApi() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/archetypes.php',)
        .then(response => (this.store.ArrArchetypes = response.data));
    }
  },

  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0', {
        params: {
          archetype_name: this.store.SearchArchetypes,
        }
      })
      .then(response => (this.store.CardsList = response.data.data));

    this.requestDataFromApi();

  },
};
</script>

<template>
  <header>
    <AppTitle />
  </header>

  <main>
    <FilterCards @performSearch="this.requestDataFromApi" />
    <FilterResults />
    <CardsList />
  </main>
</template>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";

main {
  background-color: #D48F38;
}
</style>