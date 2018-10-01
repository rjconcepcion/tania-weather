<template>
  <div id="app">
    <v-container fluid>
      <v-layout row wrap>
        <v-flex xs12 sm12 md12 lg12 xl12 class="cyan lighten-4">
            <v-icon xs12 sm12 md12 lg12 xl12 :size="'500px'">mic</v-icon>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import Artyom from "artyom.js"
const artyom = new Artyom();
export default {
  name: 'App',
  methods: {
    initialize() {
      artyom.initialize({
        continuous:true,
        lang:"en-US",
        listen:true,
        debug:true,
        speed: 1
      }).then(() => {
        console.log("Ready to speak!");
      });
    },
    speakNow(msg) {
      artyom.say(msg, {
        onStart: () => {
          console.log("The text is being readed");
        },
        onEnd: () => {
          console.log("Finished!");
        }
      });
    },
  },
  mounted() {
    this.initialize()
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 100%;
  height: 100vh;
  margin-top: 0px;
  background-color: #b2ebf2!important;
  border-color: #b2ebf2!important;
}
</style>
