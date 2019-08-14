<template>
  <div id="app">
    <Home
      v-bind:state="state"
      v-bind:handleGreet="handleGreet"
    />
  </div>
</template>

<script>
import Home from "./Home";

export default {
  name: "app",
  components: {
    Home
  },
  methods: {
    handleGreet: function(event) {
      this.state.seen = !this.state.seen;
    }
  },
  data() {
    return {
      state: {
        msg: "Hello World",
        greet: "Good Evening",
        seen: true,
        todos: [
          { text: "Learn JavaScript" },
          { text: "Learn Vue" },
          { text: "Build something awesome" }
        ]
      }
    };
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: round;
  padding: 0;
}

li {
  // display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
