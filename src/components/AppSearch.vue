<script>
import { store } from '../store.js';

export default {
    name: "AppSearch",
    data() {
        return {
            store
        }
    },
}
</script>
<template lang="">
    <div class="d-flex">
        <select class="form-select" id="select_option" v-model="store.archetype">
            <option value="" selected>Select Archetype</option>
            <option v-for="archetype, index in store.archetypes" :key="index" :value="archetype.archetype_name">
                {{ archetype.archetype_name }}
            </option>
        </select>

        <button type="button" class="btn btn-success mx-4" @click="$emit('sendSearch')">Search</button>
    </div>
</template>
<style lang="scss" scoped>
#select_option {
    width: 300px;
}
</style>