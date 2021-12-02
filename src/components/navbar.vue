<template>
<v-toolbar
  color="#ffff"
  tile
  
>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color='transparent'
          v-bind="attrs"
          v-on="on"
          style='box-shadow:none; width:3rem;'
        
        >
        <v-icon >mdi-menu</v-icon>
        </v-btn>
      </template>
      <v-list class="burgarmeny">
          <v-list-item>
            <router-link
            to="/shop"
            v-slot="{href, route, navigate}"
            >
            <button :href="href" @click="navigate">
                <h4>{{ route.name }}</h4>
            </button>
            </router-link>
          </v-list-item>

          <v-list-item>
            <router-link
            to="/contact"
            v-slot="{href, route, navigate}"
            >
            <button :href="href" @click="navigate">
                <h4>{{ route.name }}</h4>
            </button>
            </router-link>
          </v-list-item>

            <v-list-item>
            <router-link
            to="/blog"
            v-slot="{href, route, navigate}"
            >
            <button :href="href" @click="navigate">
                <h4>{{ route.name }}</h4>
            </button>
            </router-link>
          </v-list-item>
          <v-divider></v-divider>

          <v-list-item style="margin-top: 1rem;">
            <router-link
            to="/account"
            v-slot="{href, navigate}"
            >
            <button :href="href" @click="navigate" style="display: grid; grid-template-columns: 1fr 2fr; color: grey;">
                <v-icon color="grey lightend-2">mdi-account</v-icon><p>Account</p>
            </button>
            </router-link>
          </v-list-item>

          <v-list-item>
              <v-menu offset
              :close-on-content-click="closeOnContentClick">
                <template v-slot:activator="{ on, attrs }">
                <button
                color='transparent'
                v-bind="attrs"
                v-on="on"
                style='box-shadow:none; display: grid; grid-template-columns: 1fr 2fr; color: grey;'
                >
                <v-icon color="grey lightend-2">mdi-magnify</v-icon><p>Search</p>
                </button>
                </template>
                <v-text-field
                    placeholder="Search"
                    filled
                    rounded
                    dense
                    background-color="#ffff"
                    type="text"
                    id="name"
                    size="9"
                    >
                </v-text-field>
              </v-menu>

          </v-list-item>





      </v-list>
    </v-menu>

    <div class="loggo">
        <v-img
        src="@/assets/loggo.png"
        max-height="50"
        max-width="90"
        object-fit
        ></v-img>
        
    </div>

    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color='transparent'
          v-bind="attrs"
          v-on="on"
          style='box-shadow:none; width:3rem; margin-left:3rem;'
        
        >
        <v-icon >mdi-shopping</v-icon>
        </v-btn>
      </template>
      <v-list>
        
      </v-list>
    </v-menu>
</v-toolbar>
</template>

<script>

export default {

    data: () => ({
      closeOnContentClick: false,
    }),
    

    // document.getElementById("name").setAttribute('size', '20');

}
</script>

<style>
.toppnav {
    width: 100%;
    margin: auto;
}


.v-toolbar__content {
    display: grid !important;
    grid-template-columns: 1fr 1fr 1fr;
    margin: auto;
    padding: 0% !important;
}

.loggo {
    display: grid;
    justify-content: center;
  
}

.burgarmeny {
    width: 10rem;
}

.v-menu__content {
  box-shadow: none !important;
}


</style>