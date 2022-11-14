<script>
import CharaterListVue from './CharactersList.vue'
export default {
    name: 'AppMain',
    components: { CharaterListVue },
}
</script>
<template>
    <main>
        <div class="category my-5 container">
            <div class="btn btn-light "> Select category <i class="fa-solid fa-chevron-down"></i></div>
        </div>


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