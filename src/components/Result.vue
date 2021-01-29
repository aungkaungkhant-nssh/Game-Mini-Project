<template>
  <p>The result is {{score}} ms</p>
  <div v-if="score<250">
      <p>You are very fast nice!</p>
  </div>
  <div v-else-if="score>250 && score<500">
      <p>You are normal</p>
  </div>
  <div v-else>
      <p>You are very slow</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>