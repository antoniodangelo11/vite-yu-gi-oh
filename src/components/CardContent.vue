<script>
export default {
    props: {
        cardData: Object,
    }
}
</script>

<template>
    <div>
        <img :src="cardData.card_images[0].image_url_small" :alt="cardData.id">
        <h3 class="name">{{ cardData.name }}</h3>
        <div class="archetype">{{ cardData.archetype }}</div>
    </div>
</template>

<style lang="scss" scoped></style>