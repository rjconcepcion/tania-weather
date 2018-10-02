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
const speakNow = (msg)  => {
      artyom.say(msg, {
        onStart: () => {
          console.log("The text is being readed");
        },
        onEnd: () => {
          console.log("Finished!");
        }
      });
    }
export default {
  name: 'App',
  data: () => ({
    allCommands: [
      {
        indexes:["hello","good morning","hey"], // These spoken words will trigger the execution of the command
        action:() => { // Action to be executed when a index match with spoken word
          speakNow('Hello, im Tanya your virtual weather channel in Bulacan.');
        }
      }
    ]
  }),
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
    command() {
      artyom.addCommands(this.allCommands);
    }
  },
  mounted() {
    this.initialize()
    this.command()
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
