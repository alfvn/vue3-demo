<template>
  <div id="app">
    <input type="text" v-model="val" @keyup.enter="addTodo">
    <ul>
      <li v-for="todo in todos" :key="todo.id">{{todo.title}}</li>
    </ul>
  </div>
</template>

<script setup>
import {reactive, ref, toRefs} from 'vue'

export default {
  setup(){
    // 列表功能
    let val = ref('')
    let todos = reactive([ 
        {id:0, title:'吃饭', done:false},
        {id:1, title:'睡觉', done:false},
    ])
    function addTodo(){
      todos.push({
        id:todos.length,
        title:val.value,
        done:false
      })
      val.value = ''
    }
    export {val, todos, addTodo} //最新版都不需要写export了，这个提案社区皆大欢喜，和Svelte越来越像了。
    // 其他功能
  }
}
</script>