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
    >      <span>Create by suchnaun wannapinyo 6104101393 Maejo University</span>
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
<style>
  .theme--dark.v-application {
    background-image:url('https://cdn.dribbble.com/users/6616/screenshots/1458875/rocket.gif');
    background-size: cover;
}
</style>
