<script>
import axios from 'axios';
import AppCard from "./AppCard.vue";

import { store } from '../store.js';

export default {
    name: "CharactersList",
    components: {
        AppCard
    },
    data() {
        return {
            store
        }
    },
    methods: {
        getCharactersList() {
            axios.get(store.endpoint).then((response) => {
                this.store.charactersData = response.data.data
            })
        }
    },
    created() {
        this.getCharactersList();
    },
}
</script>
<template lang="">
    <AppCard  v-for="(cards, index) in store.charactersData" :key="index" :cards="cards"></AppCard>
</template>
<style lang="">

</style>