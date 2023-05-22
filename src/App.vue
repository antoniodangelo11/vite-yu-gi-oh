<script>
import AppTitle from './components/AppTitle.vue';
import FilterCards from './components/FilterCards.vue';
import CardsList from './components/CardsList.vue';
import FilterResults from './components/FilterResults.vue';
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
    CardsList,
    FilterResults,
  },
  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(response => (this.store.CardsList = response.data.data));
  },
};
</script>

<template>
  <header>
    <AppTitle />
  </header>

  <main>
    <FilterCards />
    <CardsList />
    <FilterResults />
  </main>
</template>

<style lang="scss"></style>