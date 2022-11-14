<script>
import CharaterItemVue from './CharacterItem.vue';
import { store } from '../store.js'
export default {
    name: 'CharaterList',
    components: {
        CharaterItemVue
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container py-5 bg-white">
        <div class="found bg-dark text-white py-2 px-2">Found 62 chacartes</div>
        <div class="row row-cols-sm-5">
            <CharaterItemVue :character="character" v-for="character in store.characters"></CharaterItemVue>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container {
    width: 80%;
}
</style>