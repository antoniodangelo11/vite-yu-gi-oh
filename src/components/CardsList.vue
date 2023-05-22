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
    <div class="cards_container">
        <CardContent v-for="card in store.CardsList" :key="card.id" class="card" :cardData="card" />
    </div>
</template>

<style lang="scss" scoped></style>