<template>
  <li class="text">{{todo.text}}</li>
</template>

<script>
export default {
  props: ['todo']
}
</script>

<style scoped>
.text {
  color: #f60;
  text-align: left;
}
</style>
