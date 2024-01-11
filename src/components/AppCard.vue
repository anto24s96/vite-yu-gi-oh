<script>
export default {
    name: "AppCard",
    props: {
        cards: Object
    }
}
</script>
<template lang="">
    <div class="card">
        <!-- <img v-for="cardImgs in cards.card_images" :src="cardImgs.image_url_small" alt="images"> --> 
        <img :src="cards.card_images[0].image_url_small" alt="images"> <!-- MODO PIU SEMPLICE ATTRAVERSO L'INDICE -->
        <div id="card_name">{{ cards.name }}</div>
        <div id="card_archetype">{{ cards.archetype }}</div>
    </div>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card {
    margin: 20px;
    width: calc(100% / 5 - 40px);
    text-align: center;
    background-color: #d48f38;

    img {
        border: 3px solid red;
    }

    #card_name {
        text-transform: uppercase;
        color: white;
        font-weight: bolder;
        font-size: 22px;
        margin: 10px 0;
    }

    #card_archetype {
        font-size: 22px;
        margin: 15px 0;
    }
}
</style>