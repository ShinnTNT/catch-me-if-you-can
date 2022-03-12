<template>
<p>Result is {{score}}</p>
<div v-if="score<250">
  <p>You are too fast</p>
</div>

  <div v-if="score>250 && score<500">
    <p>You are just normal</p>
  </div>

  <div v-if="score>500">
    <p>You are too slow</p>
  </div>
</template>

<script>
export default {
  name: "Result",
  props:['score']
}
</script>

<style scoped>

</style>