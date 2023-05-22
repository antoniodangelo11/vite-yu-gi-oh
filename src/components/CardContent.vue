<script>
export default {
    props: {
        cardData: Object,
    }
}
</script>

<template>
    <div class="card_x rounded">
        <div class="img_container">
            <img :src="cardData.card_images[0].image_url" :alt="cardData.id">
        </div>
        <div class="img_text py-2">
            <div class="text-light fw-bold">{{ cardData.name }}</div>
            <div class="py-1 fw-bold">{{ cardData.archetype }}</div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card_x {
    background-color: #D48F38;
    margin: 2rem 1rem;
    width: calc((100% / 5) - 2rem);

    .img_container {
        width: 100%;

        img {
            width: 100%;
        }
    }

    .img_text {
        width: 100%;
        text-align: center;
        font-size: .8em;
    }
}
</style>