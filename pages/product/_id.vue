<template>
  <div> <v-card-text>
      <p class="display-1 text--primary">
        {{ this.$route.params.id.data[0].title }}
      </p>
    </v-card-text>
    <v-card
    class="mx-auto"
    color="teal"
    width="2000px"
  >
    <v-card-text>
    Description : {{ this.$route.params.id.data[0].description }} <br><br>
    Nasa_id : {{ this.$route.params.id.data[0].nasa_id }} <br><br>
    Center : {{ this.$route.params.id.data[0].center }} <br><br>
    Date_created : {{ this.$route.params.id.data[0].date_created }} <br><br>
    Keywords : {{ this.$route.params.id.data[0].keywords }} <br><br>
    </v-card-text>
  </v-card>
  </div>
</template>
