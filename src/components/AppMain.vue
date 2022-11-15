<script>
import CharaterListVue from './CharactersList.vue'
export default {
    name: 'AppMain',
    components: { CharaterListVue },
}
</script>
<template>
    <main>

        <section class="charaters my-3">

            <CharaterListVue />
        </section>
    </main>
</template>

<style lang="scss">
.container {
    width: 80%;
}
</style>