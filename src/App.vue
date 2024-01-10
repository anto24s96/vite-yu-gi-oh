<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

import { store } from './store.js';

export default {
    components: {
        AppHeader,
        AppMain
    },
    data() {
        return {
            store
        }
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