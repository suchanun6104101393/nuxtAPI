<template>
  <div>  <v-row justify="center">
    <v-col
      cols="12"
      md="3"
    >
    <v-btn x-large color="lime" class="headline font-weight-bold">
        {{ this.$route.params.id.data[0].title }}
         <v-icon dark>
          mdi-heart
         </v-icon>
    </v-btn>
    </v-col>
  </v-row>
    <v-card
    class="mx-auto"
    color="deep-purple"
    width="2000px"
  >
    <v-card-text class="font-weight-black">
    Description : {{ this.$route.params.id.data[0].description }} <br><br>
    Nasa_id : {{ this.$route.params.id.data[0].nasa_id }} <br><br>
    Center : {{ this.$route.params.id.data[0].center }} <br><br>
    Date_created : {{ this.$route.params.id.data[0].date_created }} <br><br>
    Keywords : {{ this.$route.params.id.data[0].keywords }} <br><br>
    </v-card-text>
  </v-card>
  </div>
</template>
