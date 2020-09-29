<template lang="html">
  <div>
    <v-toolbar
      dark
      prominent
      src="https://swot.jpl.nasa.gov/system/feature_items/images/38_orbit_cropped.gif"
    >
      <v-toolbar-title>NASA</v-toolbar-title>
      <v-spacer />
    </v-toolbar>
    <v-text-field v-model="query" label="SEARCH ABOUT NASA (ENGLISH ONLY)" />
    <v-btn block rounded color="cyan darken-1" @click="handleSearchNasa">
      <v-icon dark>
        mdi-heart
      </v-icon>
      Search
      <v-icon dark>
        mdi-heart
      </v-icon>
    </v-btn>
    <br><br>
    <v-row justify="center">
      <v-card
        v-for="list in nasa"
        :key="list.items"
         width="344"
        class="ml-6 mb-6"
      >
        <nuxt-link :to=" {name: 'product-id', params: { id: list }} ">
          <v-img :src="list.links[0].href" height="194" />
          <v-btn  block color="pink darken-1" rounded >
            <v-icon>mdi-star</v-icon>
            Click
            <v-icon>mdi-star</v-icon>
          </v-btn>
        </nuxt-link>
      </v-card>
    </v-row>
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
        this.nasa = response.data.collection.items.slice(0, 36)
      })
    }
  }
}
</script>
