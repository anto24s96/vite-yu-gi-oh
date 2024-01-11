<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

import axios from 'axios';
import { store } from './store.js';

export default {
    components: {
        AppHeader,
        AppMain,
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
    <div>
        <AppHeader></AppHeader>
        <AppMain></AppMain>
    </div>
</template>
<style lang="scss">
@use "./styles/generals.scss" as *;
</style> 