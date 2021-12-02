<template>
<div>
    <div class="container">
     <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
  <h2 style="text-align:center;">Welcome back</h2>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

    <v-text-field
      v-model="password"
      :rules="passwordRules"
      label="Password"
      required
    ></v-text-field>

    <v-btn
      :disabled="!valid"
      color="pink lighten-5"
      class="loginbtn"
      @click="validate"
    >
      Log in
    </v-btn>

  </v-form>

</div>
<Register/>
<div class="accimg">
    <div class="shoplink">
        <h2>SOMETHING NEW?</h2>
        <router-link
            to="/shop"
            v-slot="{href, navigate}"
            >
            <button 
            :href="href" @click="navigate"
            style="border: 2px solid black !important; box-shadow: none; width: 10rem; margin:auto; border-radius: 2px;"
            color="transparent" >
            <h5 style="padding: 0.5rem; color:black;">SHOP NOW</h5>
            </button>
        </router-link>
    </div>
</div>

</div>

</template>

<script>
import Register from '../components/registration.vue'

  export default {
      components: {
          Register
      },
    data: () => ({
      valid: true,
      password: '',
      passwordRules: [
        v => !!v || 'Password is required',
        v => (v && v.length <= 8) || 'Password must be 8 or more characters',

      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
    }),
    methods: {
      validate () {
        this.$refs.form.validate()
      },
    },
  }
</script>

<style>
.container {
    width: 80vw;

}

.loginbtn {
    box-shadow: none;

}

.v-form {
    display: grid;
    grid-template-rows: 1fr 1fr;
}

.accimg {
    height: 100vw;
    background-image: url(https://images.unsplash.com/photo-1619260464579-58cf308df561?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MXx8Ym9obyUyMGNoaWN8ZW58MHx8MHx8&w=1000&q=80);
    background-size: cover;
    background-position: center;
    /* display: flex; */
    /* align-items: center; */
    /* justify-items: center; */
    /* grid-template-rows: 1fr 2fr; */

}

.shoplink {
    display: grid;
    justify-items: center;
    padding-top: 2rem;
    /* width: 50vw; */
}
</style>