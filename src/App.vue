
<template>
  <div id="app">
    <p v-bind:style="{ 'font-size': `${size}px` }">
      {{ name }} <span v-text="surname"></span>
    </p>

    <button @click="toggleName">Change name</button>
 
  </div>
</template>

<script>

import HelloWorld from './components/HelloWorld.vue';

export default {
    name: "App",
    data() {
        return {
            name: "Simi",
            surname: "Da-Walang",
            size: 50,
        };
    },
    methods: {
      toggleName() {
        this.name = 'Siri'
      }
    },
    components: HelloWorld,
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
