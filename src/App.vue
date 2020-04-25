<template>
  <div>
    <h1>Witaj systemie zapisow na zajecia</h1>
    <div v-if="authenticatedUsername != ' '">
        <h3>Jestes zalogowany jako: {{ authenticatedUsername}}</h3>
        <a @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else>
        <input type="text" v-model="email">
        <button @click="logMeIn()">Zaloguj</button>
    </div>
  </div>
</template>
<script>
import "milligram";

export default {
  data() {
    return {
      email: '',
      authenticatedUsername: ''
    };
  },
  methods: {
    logMeIn() {
      this.authenticatedUsername = this.email;
      this.email = ' ';
   },
   logMeOut() {
     this.authenticatedUsername = " ";
   }
  }
}
</script>

<style>
</style>
