<script>
import CardContent from './CardContent.vue';
import { store } from '../store';

export default {
    data() {
        return {
            store,
        };
    },
    components: {
        CardContent,
    },
};
</script>

<template>
    <div class="cards_container d-flex flex-wrap bg-light">
        <CardContent v-for="card in store.CardsList" :key="card.id" :cardData="card" />
    </div>
</template>

<style lang="scss" scoped>
.cards_container {
    max-width: 1200px;
    margin: auto;
    background-color: white;
}
</style>