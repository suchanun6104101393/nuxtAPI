<template lang="html">
  <div>
    <div>
      <v-toolbar
      dark
      prominent
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    >

      <v-toolbar-title>Vuetify</v-toolbar-title>

      <v-spacer></v-spacer>
    </v-toolbar>
      <v-text-field v-model="query" label="SEARCH ABOUT NASA (ENGLISH ONLY)" />
      <v-btn large @click="handleSearchNasa" color="error">
        Search
      </v-btn>
        <v-progress-circular
          indeterminate
          color="primary"
    ></v-progress-circular>

    <v-progress-circular
          indeterminate
          color="red"
    ></v-progress-circular>

    <v-progress-circular
          indeterminate
          color="purple"
    ></v-progress-circular>

    <v-progress-circular
          indeterminate
          color="green"
    ></v-progress-circular>

    <v-progress-circular
          indeterminate
          color="amber"
    ></v-progress-circular>
    </div>
    <div v-for="list in nasa" :key="list.items">
      <!-- {{list}} -->
      <nuxt-link :to=" {name: 'product-id', params: { id: list }} ">
        <img :src="list.links[0].href">
      </nuxt-link>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      query: '',
      nasa: ''
    }
  },
  methods: {
    handleSearchNasa () {
      const url = 'https://images-api.nasa.gov/search?q=' + this.query + ''
      axios.get(url).then((response) => {
        this.nasa = response.data.collection.items.slice(1, 20)
      })
    }
  }
}
</script>
<style lang="css" scoped></style>
