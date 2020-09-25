<template>
  <div id="app">
    <b-container fluid class="bv-example-row mb-3">
      <img alt="logo" width="25%" src="./assets/logo.png" />
    </b-container>
    <br />
    <musicapp />
  </div>
</template>
<script>
import musicapp from "./components/musicapp";
export default {
  name: "App",
  components: {
    musicapp,
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f36ea6;
}
body {
  background-image: url("./assets/bg.jpg");
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-size: 100% 100%;
  height: 100vh;
}
/* body {background: bottom;} */
</style>
