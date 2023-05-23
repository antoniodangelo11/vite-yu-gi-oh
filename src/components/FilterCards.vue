<script>
import { store } from '../store';

export default {
    data() {
        return {
            store,
        }
    },
    methods: {
        emitArchetypes() {
            this.$emit('performSearch');
        },
    },
};
</script>

<template>
    <div class="filter_cards">
        <select v-model="store.SearchArchetypes" @change="emitArchetypes">
            <option value="">Select Archetypes</option>
            <option v-for="archetype in store.ArrArchetypes" :key="archetype.archetype_name"
                :value="archetype.archetype_name">
                {{ archetype.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
.filter_cards {
    margin-left: 100px;
}
</style>