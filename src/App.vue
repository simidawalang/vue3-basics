<template>
  <div id="app">
    <p v-bind:style="{ 'font-size': `${size}px` }" v-bind:id="nameID">
      {{ name }} <span v-text="surname"></span>
    </p>

    <button @click="toggleColor">Change color</button>
    <span v-bind:class="isRed ? 'red-text' : ''">Red</span>

    <span v-bind:class="['bold-font', 'red-text']">Red and Bold</span>
    <ul v-for="(name, index) in nameList" :key="index">
      <li>{{ index }} {{ name }}</li>
    </ul>

    <h3>Actors</h3>
    <ul v-for="(actor, index) in actors" :key="index">
      <div>
        <li>{{ actor.name }}</li>
        <p v-for="movie in actor.movies" :key="movie">{{ movie }}</p>
      </div>
    </ul>

    <div v-for="word in partsOfSpeech" :key="word.name"><p>{{ word.name }}</p></div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      nameID: "name-id",
      name: "Simi",
      surname: "Da-Walang",
      size: 50,
      isRed: false,
      nameList: ["Segun", "Moralis", "Jara"],
      actors: [
        {
          name: "Tom Cruise",
          movies: ["Mission Impossible", "Die Another Day"],
        },
        {
          name: "Johnny Depp",
          movies: ["Pirates of the Carribean", "The Tourist"],
        },
      ],
      partsOfSpeech: [
        { name: "cat", type: "noun" },
        { name: "big", type: "adjective" },
        { name: "purple", type: "noun"}
      ],
    };
  },
  methods: {
    toggleName() {
      this.name = "Siri";
    },
    toggleColor() {
      this.isRed = !this.isRed;
    },
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

.red-text {
  color: red;
}

.bold-font {
  font-weight: bold;
}
</style>
