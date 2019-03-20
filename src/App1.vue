<template>
  <div id="app">
    {{message}}
    <ul v-for="(item, index) in todoList" :key='index'>
      <TodoItem :todo='item'/>
    </ul>
    <Props 
      :name='pname'
      :list='todoList'
      :type='typeValue'
      :isVisible='visibleMark'
      :onChange='changeEvent'
      custom='sss'
      class="parent-class"
    ></Props>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'
import Props from './views/1.1/Props'

export default {
  name: 'app',
  components: {
    TodoItem,
    Props
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
      ],
      typeValue: 'success',
      pname: 'hi vue',
      visibleMark: true
    }
  },
  methods: {
    changeEvent(e){
      // eslint-disable-next-line 
      console.log('伏组件的是', e)
      this.typeValue = e
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
.parent-class{
    color: aqua;
}
</style>
