<script>
import CharactersList from './CharactersList.vue';

export default {
    name: "AppMain",
    components: {
        CharactersList
    }
}
</script>
<template lang="">
    <main>
        <div class="yugi-container container d-flex">
            <CharactersList></CharactersList>
        </div>
    </main>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.yugi-container {
    background-color: rgb(39, 39, 39);
    margin-top: 50px;
    margin-bottom: 30px;
    flex-wrap: wrap;
    padding: 20px;
}
</style> 