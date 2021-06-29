<template>
  <div class="to-do-container">
    <div class="create-container">
      <input v-model="titleOfNewToDo" type="text">
      <button @click="create">
        Add
      </button>
    </div>
    <div class="to-do-list-container">
      <to-do-list-item v-for="todo in todos" :key="todo.id" :todo="todo" v-on:delete="deleteItem" />
    </div>
    <div class="to-do-list-container">
    </div>
  </div>
</template>

<script>
import ToDoItemCreate from '~/components/ToDoItemCreate.vue'
import ToDoListItem from '~/components/ToDoListItem.vue'

export default {
  components: {
    ToDoItemCreate,
    ToDoListItem
  },
  props: {
    todos: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    createItem (item) {
      this.todos.push(item)
    },
    deleteItem (item) {
      this.todos.splice(this.todos.indexOf(item), 1)
    }
  }
}
</script>

<style lang="scss">
</style>
