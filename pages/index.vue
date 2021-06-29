<template>
  <div class="container">
    <h1 class="title">
      My To Do List
    </h1>
    <to-do-list :todos="todos" />
  </div>
</template>
<script>
import ToDoList from '~/components/ToDoList.vue'
export default {
components: {
ToDoList
},
data () {
    return {
      todos: {
        type: Array
      }
    }
  },
  asyncData (ctx) {
    return {
      todos: [
        {
          'id': '1',
          'title': 'A',
          'completed': false
        },
        {
          'id': '2',
          'title': 'B',
          'completed': true
        }
      ]
    }
  }
}
</script>
<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
  Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
  "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 64px;
  color: #35495e;
  letter-spacing: 1px;
  margin-top: 20px;
  text-align: center;
}

</style>
