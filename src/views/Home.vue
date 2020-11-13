<template>
  <div class="home">
    <v-container
      style="    display: inline-flex;
    flex-direction: column;
    height: 100%;"
    >
      <img src="../assets/bed.png" alt />
      <div class="home-desk">
        <div id="nav">
          <img src="../assets/law.png" alt />
          <h2>Sleepy Head</h2>

          <v-btn
            style="  background: #73727a;font-size: 12px; color: white;"
            class="write"
            @click.stop="dialog = true"
            >создать пост</v-btn
          >
          <router-link style="color:black;text-decoration:underline;" to="/exit"
            >выход</router-link
          >
          <v-dialog v-model="dialog" @click="makePost()" max-width="700">
            <v-card>
              <v-card-title class="headline"
                >Что вам сегодня приснилось?</v-card-title
              >
              <h4>Заголовок</h4>
              <v-col center cols="20" sm="6" md="10">
                <v-text-field
                  label="Solo"
                  v-model="editedTit"
                  @click="editTitle()"
                  solo
                ></v-text-field>
              </v-col>
              <h4>Описание</h4>
              <v-col cols="20" md="10">
                <v-textarea
                  solo
                  name="input-19-10"
                  label="Solo textarea"
                  v-model="dreamDesEdit"
                ></v-textarea>
              </v-col>

              <v-card-actions>
                <v-spacer></v-spacer>

                <v-btn color=" darken-1" text @click="dialog = false"
                  >отменить</v-btn
                >

                <v-btn color="darken-1" text @click="saveAndclose"
                  >сохранить</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-dialog>
        </div>
        <div class="dreams">
          <div class="dreams-story">
            <h4>{{ dreamTitle }}</h4>
            <p>{{ dreamDescription }}</p>
          </div>
        </div>
      </div>
    </v-container>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Registration from "@/components/Registration.vue"; // @ is an alias to /src
import Exit from "@/components/Exit.vue";
@Component({
  components: {
    Registration
  }
})
export default class Home extends Vue {
  dialog = false;
  editedTit = "";
  dreamDesEdit = "";
  dreamTitle = "";
  dreamDescription = "";
  editTitle() {
    this.editedTit = "";
  }
  makePost() {
    this.editedTit = "";
    this.dreamDesEdit = "";
  }
  saveAndclose() {
    this.dreamTitle = this.editedTit;
    this.dreamDescription = this.dreamDesEdit;
    this.dialog = false;
  }
}
</script>
<style lang="scss">
.v-sheet.v-card {
  background: rgba(229, 229, 229, 0.68);
  border: 1px solid #000000;
  box-sizing: border-box;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  height: 100%;
}
.home {
  height: 100%;
  & img {
    height: 100%;
  }
  &-desk {
    position: absolute;
    width: 100%;
    height: 100%;
    margin: 0 auto;
    left: 0;
  }
}
.dreams {
  background: rgba(115, 114, 122, 0.58);
  border-radius: 10px;
  width: 70%;
  height: 60%;
  margin: 0 auto;
  display: inline-flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  &-story {
    height: 30%;
    width: 80%;

    background: white;
    border-radius: 10px;
    display: inline-flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    overflow-x: auto;

    & p {
      text-align: center;
      width: 90%;
      height: 100%;
      overflow-x: auto;
    }
  }
}
#nav {
  height: 25%;
  display: flex;

  padding: 30px;
  width: 95%;
  justify-content: space-between;

  align-items: center;
  & img {
    height: 100%;
  }
}
.write {
  mix-blend-mode: color-burn;
  border-radius: 10px;
}
</style>
