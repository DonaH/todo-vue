<template>
  <div id="app">
    <h1 class="ui dividing centered header">Vue.js Todo App</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
  </div>
</template>

<script>
  import sweetalert from 'sweetalert';
  import TodoList from './components/TodoList';
  import CreateTodo from './components/CreateTodo';

  export default {
    name: 'app',
    components: {
      TodoList,
      CreateTodo,
    },
    data() {
      return {
        todos: [{
          title: 'Todo A',
          project: 'Project A',
          done: false,
        }, {
          title: 'Todo Is Done',
          project: 'Project B',
          done: true,
        }, {
          title: 'New Vue App Needed',
          project: 'Project C',
          done: false,
        }, {
          title: 'Light At The End Of The Tunnel',
          project: 'Project D',
          done: false,
        }],
      };
    },
    methods: {
      createTodo(newTodo) {
        this.todos.push(newTodo);
        sweetalert('Success!', 'To-Do created!', 'success');
      },
    },
  };
</script>
