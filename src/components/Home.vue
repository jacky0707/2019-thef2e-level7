<template>
  <v-container>
    <v-row justify="center">
      <v-col class="col-sm-6 col-12">
        <v-card>
          <v-img
            src="../assets/pic/ceiling-chairs-coffee-shop-1863622-2.jpg"
            gradient="to top right, rgba(0,0,0,.7), rgba(0,0,0,.7)"
          >
            <v-img src="../assets/pic/logo.png" class="ma-5"></v-img>
            <v-row justify="center">
              <v-col v-for="(item,index) in peoplePicSrc" :key="index" cols="4" class="py-0">
                <v-hover v-slot:default="{ hover }">
                  <v-card
                    :elevation="hover ? 12 : 2"
                    color="blue-grey darken-4"
                    class="pa-2 cursor"
                  >
                    <v-card color="blue-grey lighten-4" class="pa-1">
                      <v-card color="blue-grey darken-4" class="pa-3">
                        <v-img v-bind:src="item" aspect-ratio="1" contain></v-img>
                      </v-card>
                    </v-card>
                  </v-card>
                </v-hover>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col cols="auto" class="py-0">
                <v-radio-group v-model="radioGroup" dark>
                  <v-radio label="我要匿名" value="without-name"></v-radio>
                  <v-radio label="使用暱稱" value="with-name"></v-radio>
                </v-radio-group>
              </v-col>
            </v-row>
            <v-row justify="center" v-if="radioGroup == 'with-name'">
              <v-col cols="6" class="py-0">
                <v-text-field dark solo></v-text-field>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col cols="6" class="py-0">
                <v-btn color="orange lighten-3" block rounded>開始聊天</v-btn>
              </v-col>
            </v-row>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import onePeople from "../assets/icon-one@2x.png";
import people from "../assets/icon-people@2x.png";

export default {
  data: () => ({
    radioGroup: "without-name",
    peoplePicSrc: [onePeople, people]
  }),
  methods: {}
};
</script>
<style scoped>
.cursor {
  cursor: pointer;
}
</style>