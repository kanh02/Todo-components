<template>
  <div id="app">
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:add-todo="addTodo"/>
</div>
</template>

<script>
import TodoList from './components/TodoList';
import Todo from './components/Todo';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        title,
        done: false,
      });
      console.log(this.todos)
    },
  },
  data(){
    return{
      todos:[{
        title:`Todo A`,
        project:`Project A`,
        done: false,
      },{
        title:`Todo B`,
        project:`Project B`,
        done: false,
      },{
        title:`Todo C`,
        project:`Project C`,
        done: false,
      },{
        title:`Todo D`,
        project:`Project D`,
        done: false,
      }]
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
