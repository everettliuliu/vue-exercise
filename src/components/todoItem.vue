<template>
  <!-- 1、绑定css样式v-bind：缩写：2、class绑定{类选择器：布尔值} -->
  <div class="todo-item" :class="{'is-complete':todoElement.completed}">
    <p>
      <!-- 绑定事件监听v-on：缩写@ 2、执行方法 -->
      <input type="checkbox" @change="changeComplete" />
      {{todoElement.title}}
      <!-- 子传父用$emit('执行方法',传值) -->
      <button class="del" @click="$emit('deleteItem',todoElement.id)">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "todoItem",
  //父传子(子)用props接收数据
  props: {
    todoElement: {
      type: Object
    }
  },
  //时间监听执行方法
  methods: {
    changeComplete() {
      this.todoElement.completed = !this.todoElement.completed;
    }
  }
};
</script>
<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>