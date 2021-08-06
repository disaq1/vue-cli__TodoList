<template>
  <div id="app">
    <FirstScreen />
    <TodoList :todos="todos" @delete-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import FirstScreen from "./components/FirstScreen.vue";

export default {
  name: "App",

  data() {
    return {
      todos: [
        "Изучить vue",
        "Понять, что VUE - это КРУТО!!!!",
        "Залить в репозиторий",
        "Понять, что он не доработан",
        "Доработать",
        "Перезалить!",
      ],
    };
  },

  components: {
    TodoList,
    FirstScreen,
  },
  methods: {
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;

  min-width: 100%;
  min-height: 100vh;
}
</style>
