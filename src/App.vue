<script>
import axios from 'axios'
import AppHeaderVue from './components/AppHeader.vue'
import AppMainVue from './components/AppMain.vue'
import AppFooterVue from './components/AppFooter.vue'
import { store } from './store.js'
export default {
  name: 'App',
  components: {
    AppHeaderVue,
    AppMainVue,
    AppFooterVue,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    callApi(url) {
      axios.get(url)
        .then(response => {
          console.log(response);
          this.store.characters = response.data
        })
        .catch(err => {
          console.error(err.message)
          this.store.error = err.message
        })
    }
  },
  mounted() {
    this.callApi(this.store.API_URL)
  }
}
</script>

<template>
  <AppHeaderVue />
  <AppMainVue />
  <AppFooterVue />
</template>

<style lang="scss" scoped>
</style>