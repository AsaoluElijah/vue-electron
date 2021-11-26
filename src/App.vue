<template>
  <div id="app">
    <div class="d-flex my-3">
      <button class="btn btn-primary rounded-0">Save File</button>
      <button class="btn btn-warning rounded-0 ms-2">Load File</button>
    </div>
    <textarea class="rounded" placeholder="Start typing..."></textarea>
  </div>
</template>

<script>
const { clipboard } = require("electron");
export default {
  name: "App",
  components: {},
  methods: {
    copyText() {
      clipboard.writeText("Example Text", "selection");
    },
  },
  mounted() {
    // console.log(clipboard);
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  padding: 20px;
}
textarea {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  border: 1px solid #ccc;
  padding: 10px;
  width: 100%;
  height: 80vh;
  resize: none;
}
</style>
