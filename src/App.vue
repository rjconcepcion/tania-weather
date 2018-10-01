<template>
  <div id="app">
    <v-container grid-list-{xs through xl} :fluid="true">
      <v-layout row wrap>
        <v-flex xs12 sm12 md12 class="cyan lighten-4">
            <v-icon :size="'300px'">mic</v-icon>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
