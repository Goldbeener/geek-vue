<template>
  <div>
    name: {{name || '---'}}
    <br/>
    <input :value="name" type="text" @input="hanleInput">
    <div @click="handleDiv">
      <button @click="handleSuccess">重置成功</button>
      <button @click.stop="handleSuccess">重置失败</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'EventDemo',
  props: {
    name: String
  },
  methods: {
    hanleInput(e){
      // eslint-disable-next-line
      console.log(e)
      this.$emit('changeName', e.target.value)
    },
    handleDiv(){
      let who = this.$emit('changeName', '')
      // eslint-disable-next-line
      console.log(who)
    },
    handleSuccess () {
      // e.stopPropagation()
    }
  }
}
</script>