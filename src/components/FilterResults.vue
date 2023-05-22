<script>
import { store } from '../store';

export default {
    data() {
        return {
            store,
        }
    },
};
</script>

<template>
    <div class="filter_result text-light rounded">
        <p>Found {{ store.CardsList.length }} Cards</p>
    </div>
</template>

<style lang="scss" scoped>
.filter_result {
    background-color: black;
    max-width: 200px;
    margin: auto;
    text-align: center;
}
</style>