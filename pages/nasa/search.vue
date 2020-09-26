<template lang="html">
    <div>
      <div>
      <v-text-field v-model="query" label="Search"></v-text-field>
      <v-btn @click="handleSearchNasa">Search</v-btn>
      </div>
      <v-divider class="mt-2 mb-2"></v-divider>
      <div v-for="result in results" v-bind:key="result">
        <img v-bind:src="result.links[0].href" />
    </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      query: '',
      results: ''
    }
  },
  methods: {
    handleSearchNasa () {
      const url = 'https://images-api.nasa.gov/search?q= ‘ + this.query + ‘&media_type=image'
      axios.get(url).then((response) => {
        console.log(response.data)
        console.log(response.data.collection.items)
        this.results = response.data.collection.items
      })
    }
  }
}
</script>

<style lang="css" scoped></style>
