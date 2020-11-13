<template>
  <div
    class="about"
    style=" display:flex;   
   "
  >
    <v-container>
      <div
        class="logo-reg"
        style=" display:flex;    justify-content: center;
    align-items: flex-end;"
      >
        <img style="position:relative;" src="../assets/pngegg.png" alt />
        <h2 style="position:absolute; padding-bottom:4%;">Sleepy Head</h2>
      </div>

      <v-form v-model="valid">
        <v-col class="box-reg" cols="8" md="6">
          <h1>регистрация</h1>
          <v-col class="box-reg__form" cols="12" md="6">
            <v-text-field label="введите имя" single-line solo></v-text-field>

            <v-text-field
              label="введите адрес электронной почты"
              v-model="email"
              solo
            ></v-text-field>
          </v-col>
          <v-col class="box-reg__form" cols="12" sm="6">
            <v-text-field
              v-model="password"
              :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
              :rules="[required, min]"
              :type="show1 ? 'text' : 'password'"
              name="input-10-1"
              label="придумайте пароль"
              hint="не меньше 8 знаков"
              @click:append="show1 = !show1"
            ></v-text-field>
          </v-col>
          <v-col class="box-reg__form" cols="12" sm="6">
            <div class="buttons">
              <v-btn id="reg" small>войти</v-btn>
              <v-btn id="entry" small>
                <router-link to="/">зарегестрироваться и войти</router-link>
              </v-btn>
            </div>
          </v-col>
        </v-col>
      </v-form>
    </v-container>
    <img
      style=" width:10%;height:20%; position:absolute;  
   "
      src="../assets/law.png"
      alt
    />
  </div>
</template>

<style lang="scss">
.box-reg {
  margin: 0 auto;
  background: #e5e5e5;
  border-radius: 10px;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  &__form {
    margin: 0 auto;
  }
}
.logo-reg {
  width: 30%;
  display: flex;
  margin: 0 auto;
  & img {
    width: 100%;
  }
}
.h1 {
  font-size: 48px;
  text-transform: uppercase;
  font-weight: 200;
}
#reg {
  background: #73727a;
  color: white;
}
#entry {
  background: #463f78;
  color: white;
}
.buttons {
  display: inline-flex;

  justify-content: space-between;
  width: 100%;
}
#v-btn {
  text-transform: inherit;
}
.v-text-field {
  font-size: 16px;
  text-transform: inherit;
}
</style>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

import "vuetify/dist/vuetify.min.css";
import Vuetify from "vuetify/lib";
Vue.use(Vuetify);
@Component
export default class Registration extends Vue {
  valid = false;
  password = "";
  email = "";
  show1 = false;
}
</script>

<style scoped lang="scss"></style>
