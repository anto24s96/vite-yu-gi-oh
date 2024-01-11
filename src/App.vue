<script>
import axios from 'axios';

import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';
import CharactersList from './components/CharactersList.vue';

import { store } from './store.js';

export default {
    components: {
        AppHeader,
        AppSearch,
        CharactersList
    },
    data() {
        return {
            store
        }
    },
    methods: {
        getCharactersList() {
            /*            axios.get(store.endpoint).then((response) => {
                           this.store.charactersData = response.data.data
                       }) */
            let apiUrl = store.endpoint

            if (store.archetype !== " ") {
                apiUrl = `https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.archetype}&num=100&offset=0`;
            }

            axios.get(apiUrl).then((response) => {
                store.charactersData = response.data.data;
            })
        },
    },
    created() {
        this.getCharactersList();

        axios.get(store.archetypeApi).then((response) => {
            store.archetypes = response.data;
        })
    },
}
</script>
<template lang="">
    <div>
        <AppHeader></AppHeader>
        <main>
            <div class="search_container d-flex justify-content-center py-4">
                <AppSearch @sendSearch="getCharactersList"></AppSearch>
            </div>
            <div class="yugi-container container d-flex justify-content-center">
                <CharactersList></CharactersList>
            </div>
        </main>
    </div>
</template>
<style lang="scss">
@use "./styles/generals.scss" as *;
@use './styles/partials/variables' as *;

.yugi-container {
    background-color: rgb(39, 39, 39);
    margin-bottom: 30px;
    flex-wrap: wrap;
    padding: 20px 5px;
}
</style> 