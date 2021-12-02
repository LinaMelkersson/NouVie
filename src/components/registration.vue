<template>
<div>
    <div class="regform">
        <h5>Never miss a thing!</h5>
        
        <v-btn
            icon
            @click="show = !show"
            class="missmebtn"
        >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
        </v-btn>
    </div>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <div class="container">
            <v-form
            ref="form"
            v-model="valid"
            lazy-validation
        >

            <v-text-field
            v-model="FirstName"
            :rules="FnameRules"
            label="FirstName"
            required
            ></v-text-field>

            <v-text-field
            v-model="LastName"
            :rules="LnameRules"
            label="LastName"
            required
            ></v-text-field>

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

        <!-- Confirm password, FIXA -->
            <!-- <v-text-field
            v-model="ConfirmPassword"
            :rules="passwordRules"
            label="Confirm password"
            required
            ></v-text-field> -->

            <v-checkbox
            v-model="checkbox"
            :rules="[v => !!v || 'You must agree to continue!']"
            label="Do you agree?"
            required
            ></v-checkbox>

            <v-btn
            :disabled="!valid"
            color="pink lighten-5"
            class="loginbtn"
            @click="validate"
            >
            Create account
            </v-btn>

  </v-form>
        </div>
      </div>
    </v-expand-transition>
</div>
         
</template>
     
     
<script>
  export default {
    data: () => ({
      show: false,

        valid: true,
      FirstName: '',
      FnameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
            LastName: '',
      LnameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
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
      checkbox: false,
    }),
    methods: {
      validate () {
        this.$refs.form.validate()
      },
    },
  }
</script>

<style>
.regform {
    width: 80vw;
    margin: auto;
    display: grid;
    grid-template-columns: 2fr 1fr;
    justify-items: center;
    align-items: center;
}



</style>