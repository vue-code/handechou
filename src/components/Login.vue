<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
    <v-flex>
        <v-app-bar
          class="primary">
          <div>
          <h1>Login</h1>
           </div>
        </v-app-bar>



        <v-form>
          <v-row>
            <v-col>
              <v-text-field
                v-model="username"
                :rules="[v => !!v || 'username is required']"
                label="Username"
                outlined
              >
              </v-text-field>
            </v-col>
          </v-row>
        
          <v-row>
            <v-col>
              <v-text-field
                v-model="password"
                label="Password"
                type="password"
                :rules="[v => !!v || 'password is required']"
                outlined

              >
              </v-text-field>
            </v-col>
          </v-row>
          <v-btn
            color="success"
            class="mr-8"
            @click="login"
          >
            Login
          </v-btn>
          <v-btn
            text="red"
            class="red"
            color="white"
            @contextmenu="reg"
            >
          register
          </v-btn>
        </v-form>
    </v-flex>
      
    
     
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import axios from 'axios'
import router from '../router';

export default Vue.extend({
  name: 'HelloWorld',

  data: () => ({
    username: 'hande',
    password: 'maxwit',
  }),
  
  methods: {
    login(){
      let loginForm = new FormData();
      loginForm.set("username", this.username);
      loginForm.set("password", this.password);
      axios({
        method: 'post',
        url: '/login',
        data: loginForm,
        headers: {'Content-Type': 'multipart/form-data',
        }
      });
    },
    reg() {

    },
  }
});
</script>
