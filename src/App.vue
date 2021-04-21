<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" width="25%">
    <div class="hello">
      <h3>Indica un número enter positiu:</h3>
      <input v-model="numero" type="number">
      <span style="padding-left:10px">
        <input type="button" value="insereix" @click="insereix()">
      </span>
    </div>
    <div v-if="llista.length>0">
      <h1>Llista de números</h1>
      <Number v-for="n in llista" :key="n" v-bind:numero="n" v-on:element-clickat="elementTriat"></Number>
    </div>
    <div v-if="numeroPitjat">
      <h2>El número pitjat és: {{numeroPitjat}}</h2>
    </div>
  </div>
</template>

<script>
import Number from "./components/Number.vue";

export default {
  name: "App",
  data: function() {
    return {
      numero: null,
      llista: [],
      numeroPitjat: null
    };
  },
  methods: {
    insereix: function() {
      if (this.llista.indexOf(this.numero) < 0) {
        this.llista.push(this.numero);
      }
    },
    elementTriat: function(n) {
      this.numeroPitjat = n;
    }
  },
  components: {
    Number
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
