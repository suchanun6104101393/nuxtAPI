<template>
  <v-app dark>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >      <span>create by suchnaun wannapinyo 6104101393 25/ 09/ 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {

    }
  }
}
</script>
