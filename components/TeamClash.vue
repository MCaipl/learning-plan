<template>
<div class="h-full overflow-hidden clash">
  dd
</div>

</template>

<script>
export default {
  props: ['left', 'right']
}
</script>

<style scoped>
.clash {
   background: linear-gradient(115deg, v-bind(left) 50%, v-bind(right) 50%);
}
</style>