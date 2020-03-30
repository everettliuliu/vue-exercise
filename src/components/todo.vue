<template>
  <div>
    <!-- 遍历v-for='元素 in 数组' ：key='遍历对象'-->
    <!-- 如果不使用 key，Vue 会使用一种最大限度减少动态元素并且尽可能的尝试就地修改/复用相同类型元素的算法。 -->
    <!-- 而使用 key 时，它会基于 key 的变化重新排列元素顺序，并且会移除 key 不存在的元素。 -->
    <div :key="todoElement.id" v-for="todoElement in todoList">
      <!-- 引用导入模块 -->
      <!-- 父传子 ：传值(传给子级)='传值'子传父 @执行方法(回传父级)=回调函数 -->
      <todoItem :todoElement="todoElement" @deleteItem="$emit('handleDelete',todoElement.id )" />
    </div>
  </div>
</template>
<script>
//导入模块
import todoItem from "./todoItem";
//导出模块
export default {
  name: "todosComponent",
  props: {
    todoList: {
      type: Array
    }
  },
  methods: {
    deleteItem(id) {
      console.log(id);
    }
  },
  //导入模块定义
  components: {
    todoItem
  }
};
</script>
<style scoped>
</style>