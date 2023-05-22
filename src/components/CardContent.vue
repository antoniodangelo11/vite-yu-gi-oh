<script>
export default {
    props: {
        cardData: Object,
    }
}
</script>

<template>
    <div>
        <img :src="cardData.image_url" :alt="cardData.name">
        <h3 class="name">{{ cardData.name }}</h3>
        <div class="archetype">{{ cardData.archetype }}</div>
    </div>
</template>

<style lang="scss" scoped></style>