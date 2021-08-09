<template>
  <div>
    <input type="text" v-model="inputValue" />
    <button @click="addTodo">Plus</button>
  </div>
</template>

<script>
export default {
  inputValue: "qwe",
  methods: {
    addTodo(inputValue) {
      this.$emit("add-todo", this.inputValue);
      console.log(inputValue);
    },
  },
};
</script>