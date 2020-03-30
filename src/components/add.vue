<template>
  <div class="add">
    <form @submit.prevent="addTodo">
      <input class="input" type="text" v-model="title" placeholder="请添加待办事项..." />
      <input type="submit" value="添加" class="button" />
    </form>
  </div>
</template>
<script>
//import uuid from "uuid";
export default {
  name: "addElement",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo() {
      const newTodo = {
        //id: uuid.v4(),
        title: this.title,
        complete: false
      };
      this.$emit("handleAdd", newTodo);
      this.title = "";
    }
  }
};
</script>
<style scoped>
form {
  display: flex;
}
.input {
  flex-grow: 6;
}

.button {
  display: inline-block;
  background-color: dimgray;
  border: none;
  flex-grow: 1;
}
.button:hover {
  background-color: grey;
  font-weight: bold;
}
</style>