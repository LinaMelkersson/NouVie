<template>
  <v-footer
    dark
    padless
  >
    <v-card
      flat
      tile
      class="white--text text-center"
      style="width:100%;"
    >
      <v-card-text>
          <a href="https://www.facebook.com" target="_blank" style="margin:1rem;"><v-icon>mdi-facebook</v-icon></a>
          <a href="https://www.instagram.com" target="_blank" style="margin:1rem;"><v-icon>mdi-instagram</v-icon></a>
          <a href="https://www.twitter.com" target="_blank" style="margin:1rem;"><v-icon>mdi-twitter</v-icon></a>
      </v-card-text>

      <div class="footerlink">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/contact">Contact</router-link>
      </div>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>NouVie</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
  export default {

  }
</script>

<style>
a {
    text-decoration: none;
    color: white !important;
}

.footerlink {
    display: grid;
    margin-bottom: 1rem;

}
</style>