<template>
  <div id="app">
    {{message}}
    <ul v-for="(item, index) in todoList" :key='index'>
      <TodoItem :todo='item'/>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'app',
  components: {
    TodoItem
  },
  data() {
    return {
      message: 'hello vue',
      todoList: [
        {
          text: '苹果'
        },
        {
          text: '石榴'
        },
        {
          text: '其他水果'
        }
      ]
    }
  },
}
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
