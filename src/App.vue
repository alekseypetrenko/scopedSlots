<template>
  <div id="app">
    <Parent :title="title">
      <template v-slot:child-slot>
        <h1>
          Text from the parrent and passed throught the parent to child via slot
        </h1>
        <h2>H2</h2>
        <button @click="sayHi">Click</button>
      </template>
    </Parent>
  </div>
</template>

<script>
import Parent from "./components/Parent.vue";

export default {
  name: "App",
  components: {
    Parent,
  },
  data() {
    return {
      title: "Title from App",
    };
  },
  methods: {
    sayHi() {
      this.title = "Button is clicked!";
    },
  },
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
