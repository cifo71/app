<template>
  <div class="home">
    <div class="home__inner">
      <input type="text" placeholder="Poznamka..." v-model="todo" />
      <button type="button" @click="addTodo()">Pridaj</button>
      <div v-for="(todo, index) in todoList" :key="index">
        {{ todo }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: '',
      todoList: []
    };
  },
  methods: {
    addTodo() {
      this.todoList.push(this.todo)
      this.todo = ''
    }
  }
};
</script>

<style lang="scss">
@import "~@/assets/scss/variables";
@import "~@/assets/scss/mixins";

.home {
  min-height:      100vh;
  background:      $primary;
  display:         flex;
  align-items:     center;
  justify-content: center;

  &__inner {
    display:        flex;
    flex-direction: column;

    input {
      width:         260px;
      margin-bottom: 20px;
      padding:       10px 20px;
      background:    lighten($primary, 7%);
      border:        none;
      border-radius: 6px;
      color:         $accent;
      font-size:     28px;
      @include media(sm) {
        width: 400px;
      }
      @include media(md) {
        width: 600px;
      }
    }

    button {
      padding:        10px 20px;
      background:     $secondary;
      border-radius:  6px;
      color:          $primary;
      font-size:      20px;
      font-weight:    700;
    }
  }
}
</style>
