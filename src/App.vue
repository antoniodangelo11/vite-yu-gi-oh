<script>
import AppTitle from './components/AppTitle.vue';
import FilterCards from './components/FilterCards.vue';
import CardsList from './components/CardsList.vue';
import FilterResults from './components/FilterResults.vue';

export default {
  components: {
    AppTitle,
    FilterCards,
    CardsList,
    FilterResults,
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