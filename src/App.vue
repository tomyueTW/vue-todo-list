<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
    <AddTodo v-on:add-todo="addTodo"/>
  </div>
</template>
<script>
  import Todos from './components/Todos';
  import AddTodo from './components/AddTodo';
  export default {
    name: 'app',
    components: {
      Todos,
      AddTodo
    },
    data() {
      return {
        todos: [
          {
            id: 1,
            title: '起床',
            completed: false
          },
          {
            id: 2,
            title: '騎車',
            completed: false
          },
          {
            id: 3,
            title: '上班',
            completed: false
          },
          {
            id: 4,
            title: '回家',
            completed: false
          },
          {
            id: 5,
            title: '晚餐',
            completed: false
          }
        ],
      }
    },
    methods: {
      addTodo(newTodoObj) {
        this.todos = [...this.todos, newTodoObj];
      },
      deleteTodo(todoId) {
        this.todos = this.todos.filter(todo => todo.id !== todoId);
      }
    }
  }
</script>
<style>
</style>