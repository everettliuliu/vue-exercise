<template>
  <div id="app">
    <headerComponent />
    <router-view></router-view>
  </div>
</template>



<script>
import headerComponent from "./components/header";
export default {
  name: "app",
  components: {
    headerComponent
  }
};
</script>
<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>