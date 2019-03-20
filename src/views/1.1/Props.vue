<template>
  <div class="prop-demo">
    name: {{name}}
    <br/>
    child_name: {{child_name}}
    <br />
    type: {{type}}
    <br/>
    list: {{list}}
    <br/>
    isVisible: {{isVisible}}
    <br/>
    child_visible: {{child_visible}}
    <br/>
    <button @click="handleClick">change type</button>
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
  name: 'PropsDemo',
  props: {
    name: String,
    type: {
      validator: function(value){
        return ['success', 'warning', 'danger'].includes(value)
      }
    },
    list: {
      type: Array,
      default: () => []
    },
    isVisible: {
      type: Boolean,
      default: false
    },
    onChange: {
      type: Function,
      default: () => {}
    }
  },
  data() {
    return {
      child_name: this.name
    }
  },
  computed: {
    child_visible: {
      get: function () {
        return this.isVisible + '????'
      },
      set: function (value) {
        // eslint-disable-next-line 
        console.log('计算属性发生了变化', value)
        // this.isVisible = value
      }
    }
  },
  methods: {
    handleClick(){
      this.onChange(this.type === 'success' ? 'warning' : 'success')
      this.child_name = 'I am child name' + (this.type === 'success' ? 'warning' : 'success')
      this.child_visible = (this.type === 'success' ? 'warning' : 'success')
    }
  }
}
</script>

<style scoped>
.prop-demo {
  color: blueviolet;
}
</style>
