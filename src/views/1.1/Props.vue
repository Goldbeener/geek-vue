<template>
  <div class="prop-demo">
    name: {{name}}
    <br/>
    type: {{type}}
    <br/>
    list: {{list}}
    <br/>
    isVisible: {{isVisible}}
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
  methods: {
    handleClick(){
      // eslint-disable-next-line 
      console.log('123')
      this.onChange(this.type === 'success' ? 'warning' : 'success')
    }
  }
}
</script>

<style scoped>
.prop-demo {
  color: blueviolet;
}
</style>
