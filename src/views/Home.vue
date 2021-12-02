<template>
<div>
  <div class="specialoffer">
    <h5>Special holiday offers in shop!</h5>

  </div>

  <div class="header">
    <h2 class="headertext">BOSS ASS BITCH?</h2>

      <router-link
        to="/shop"
        v-slot="{href, navigate}"
        >
        <button 
        :href="href" @click="navigate"
        style="border: 2px solid white !important; box-shadow: none; width: 10rem; margin:auto; border-radius: 2px;"
        color="transparent" >
          <h5 style="padding: 0.5rem; color:#ffff;">SHOP NOW</h5>
        </button>
      </router-link>
  </div>

  <div class="trending">
    <!-- Hitta nått som gör att bara populäraste 3 produkterna visas, eller välja 3 produkter själv -->
    <products></products>
  </div>


</div>
</template>

<script>
import products from '../components/products.vue'

  
 

  export default {
    name: 'Home',

    components: {
      products,
    }

  }
</script>

<style>
.specialoffer {
  background-color: black;
  display: grid;
  justify-content: center;
  align-content: center;
  color: white;
  height: 8vw;
  
}
.header {
  height: 75vw;
  margin: auto;
  background-size: cover;
  background-position: center;
  background-image: url(https://www.designersnexus.com/wp-content/uploads/fashion-sketches-bakcground.png);
  display: grid;
  justify-content: center;
  align-content: center;
}
.headertext {
  color: white;
}

.trending {
  margin-top: 1rem;
  margin-bottom: 1rem;
}

</style>