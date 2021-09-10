<template>
  <div>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
  
  <div id="app">
        <picture-input @change="onChange()" width="500" height="500" margin="16" accept="image/jpeg,image/png">
        </picture-input> 
</template>

<script>
import Todos from './components/Todos';
import AddTodo from './components/AddTodo'
import PictureInput from 'vue-picture-input'

export default {
  name: 'App',
  data(){
    return {
      todos:[
        {
          id:1,
          title:"todo 1",
          completed:false
        },
        {
          id:2,
          title:"todo 2",
          completed:true
        },
        {
          id:3,
          title:"todo 3",
          completed:false
        },
        {
          id:4,
          title:"todo 4",
          completed:true
        }
      ]
    }
  },
  components: {
    Todos,
    AddTodo
  },
  methods:{

    addTodo(newTodo){
      this.todos = [...this.todos,newTodo]
    },
    deleteTodo(id){
      this.todos = this.todos.filter((todo) => todo.id !== id)
    }
  }
},
export default {
    name: 'app',
    components: {
      PictureInput
    },
    methods: {
      onChange () {
        console.log("Picture changed!")
      }
    }
  };

</script>
