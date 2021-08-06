<template>
  <ul>
    <li v-for="(todo, index) in todos" @click="deleteTodo(index)" :key="index">
      {{ index + 1 }} {{ todo }}
    </li>
    <p>*Для удаления элемента из списка, нажми на него и он удалится</p>
  </ul>
</template>

<script>
export default {
  props: ["todos"],
  methods: {
    deleteTodo(index) {
      this.$emit("delete-todo", index);
    },
  },
};
</script>

<style scoped>
ul {
  border: 1px dashed #ccc;
  border-radius: 20px;

  margin: 0;
  padding: 30px;

  max-width: 700px;
  width: 100%;
  display: grid;
}

ul p {
  margin: 20px 0 0 0;
  padding: 0;

  font-size: 10px;
  color: red;
}

ul li {
  display: flex;
  list-style: none;
  margin: 10px 0 0;
  padding: 5px 0 5px 50px;
  border: 1px dotted red;
  border-radius: 30px;

  transition: 0.3s;

  font-size: 20px;
}

ul li:hover {
  cursor: pointer;
  color: white;
  background: red;
  border: 1px solid red;
}
</style>