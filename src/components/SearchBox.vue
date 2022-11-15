<script>
import { store } from '../store.js'
export default {
    name: 'SearchBox',
    components: {
        store
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h3>SELEZIONA UNA SERIE</h3>
    <select v-model="store.searchText" name="series" placeholder="">
        Selezionare una serie
        <option value="Breaking+Bad">Breaking Bad</option>
        <option value="Better+Call+Saul">Better Call Saul</option>
    </select>
    <button @click="$emit('filterSeries')" type="submit">Cerca</button>

</template>

<style lang="scss" scoped>
select,
option,
button {
   margin-right: 2rem;
    padding: 0.5rem;
    border: none;
    border-radius: 10px;
}

h3{
    color: white;
    margin-top: 2rem;
}
</style>