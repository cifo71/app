<template>
  <div>
    <input type="text" placeholder="Poznamka..." v-model="todo" />
    <button type="button" @click="addTodo()">Pridaj</button>
    <div v-for="(todo, index) in todoList" :key="index">
    {{ todo }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: "",
      todoList: []
    };
  },
  methods: {
    addTodo() {
      this.todoList.push(this.todo);
      this.todo = ''
    }
  }
};
</script>

<style lang="scss">
</style>