<template>
  <div id="app">
    <input type="text" v-model="val" @keyup.enter="addTodo">
    <ul>
      <li v-for="todo in todos" :key="todo.id">{{todo.title}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  data(){
    return{
      val:'',
      todos:[ 
        {id:0, title:'吃饭', done:false},
        {id:1, title:'睡觉', done:false},
      ]
    }
  },
  methods:{
    addTodo(){
      this.todos.push({
        id:this.todos.length,
        title:this.val,
        done:false
      })
      this.val = ''
    }
  }
}
</script>