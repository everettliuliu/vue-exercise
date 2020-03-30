<template>
  <div class="headerc">
    <h1>待办事项</h1>
    <div class="nav">
      <router-link to="/">主页</router-link>|
      <router-link to="about">关于</router-link>
    </div>
  </div>
</template>
<script>
export default {
  name: "headerComponent"
};
</script>
<style scoped>
.headerc {
  background-color: dodgerblue;
  color: black;
  text-align: center;
  padding: 10px;
}

.headerc a {
  color: black;
  text-decoration: none;
  padding-right: 5px;
}
</style>