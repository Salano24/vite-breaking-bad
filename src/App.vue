<script >
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import SearchBox from './components/SearchBox.vue'
import axios from 'axios'
import { store } from './store.js'
export default {
    name: 'App',
    components: {
        AppHeader,
        SearchBox,
        AppMain
    },
    data() {
        return {
            store
        }
    },
    methods: {
        callApi(url) {
            axios.get(url)
                .then(response => {
                    //console.log(response.data)
                    this.store.characters = response.data
                    this.store.loading = false
                })
        },
        searchSeries() {
            const categoryUrl = 'https://www.breakingbadapi.com/api/characters?category='
            //this.store.API_URL = categoryUrl + this.series
            this.store.API_URL = categoryUrl + this.store.searchText
            console.log(this.store.API_URL);
            axios.get(categoryUrl + this.store.searchText)
                .then(response => {
                    console.log(response.data);
                    this.store.characters = response.data
                    console.log(this.store.characters.length);
                    this.store.loading = false
                })
        }
    },
    mounted() {
        this.callApi(this.store.API_URL)
    }
}
</script>

<template>
    <div class="container">
        <AppHeader />
        <SearchBox @filterSeries="searchSeries" />
        <AppMain />

    </div>

</template>

<style lang="scss" scoped>
</style>