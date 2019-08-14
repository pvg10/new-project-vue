<template>
  <div id="home">
    <button v-on:click="handleGreet">Greet</button>
    <!-- {{state}} -->
    <div v-if="state.seen">
      <ul>
        <li v-for="(todo, key) in state.todos" v-bind:key="key">{{ todo.text }}</li>
      </ul>
      <form class="form">
        <input v-model="message" placeholder="Please type here...">
        <button v-on:click="onSubmit">Submit</button>
        <div class="check-select">
          <input type="checkbox" id="checkbox" v-model="checked">
          <label for="checkbox">{{ checked }}</label>
        </div>
      </form>
    </div>
    <div v-else-if="state.seen === false">
      <p>
        <strong>Toggle Again to see List Items</strong>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  props: ["state", "handleGreet"],
  methods: {
    onSubmit: function(event) {
      alert(this.message)
    }
  },
  data() {
    return {
      demo: "Hello Child Component",
      message: "",
      checked: false
    };
  }
};
</script>