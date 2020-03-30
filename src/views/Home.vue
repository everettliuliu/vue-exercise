<template>
  <div id="Home">
        
        <addElement @handleAdd="handleAdd"/>
        <todosComponent :todoList='todoList' @handleDelete="handleDelete"></todosComponent>
  </div>
</template>



<script>

import todosComponent from '../components/todo';
import addElement from '../components/add'
import axios from 'axios'
export default {
  name:'Home',
  //父传子(父)生成数据
  data(){
    return{
      msg:'message',
      todoList:[
        
      ]
    }
  },
  methods:{
    handleDelete(id){
      //console.log(id);
      //axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      //.then(res => {
        this.todoList = this.todoList.filter(todoElement => todoElement.id !== id)
      //})
      //.catch(err => console.log(err))
      // 过滤出id不等于传值id的对象
      
    },
    handleAdd(newTodo){
      //解构赋值
      //const {title,completed} = newTodo
      //axios.post("https://jsonplaceholder.typicode.com/todos",{
      //  title,
      //  completed
      //})
      //.then(  res => 
      this.todoList.unshift(newTodo)
      //  )
      //.catch(err => console.log(err))
    }
  },
  components:{
    todosComponent,
    addElement 
  },
  //生命周期钩子执行axios
  // created(){
  //   axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
  //   .then(res => {
  //     this.todoList = res.data
  //   })
  //   .catch(err => console.log(err))
  // }
}
</script>
<style>

</style>