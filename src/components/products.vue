<template>
  <v-card
    class="mx-auto"
    max-width="344"
    style="margin-top:1rem; margin-bottom:1rem;"
  >
    <v-img
      src="https://cdn.shopify.com/s/files/1/0403/5585/6552/products/1v1_siren_roots_poster_a44d5512-1cbc-4ff9-bee3-625413db5ef3_1600x.jpg?v=1635626116"
      height="200px"
    ></v-img>

    <v-card-title>
      One of a kind posters
    </v-card-title>

    <v-card-subtitle>
      Best seller
    </v-card-subtitle>

    <v-card-actions>
      <v-btn
        color="brown"
        text
      >
        Add to cart
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      show: false,
    }),
  }
</script>