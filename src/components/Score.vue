<template>
  <div>
    <p>{{ result/1000 }} s</p>
    <div v-if="result/1000 < 0.2">
      <p>You are too fast</p>
    </div>
    <div v-else-if="result/1000 < 0.5">
      <p>You are normal</p>
    </div>
    <div v-else>
      <p>You are too slow</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ['result'],
}
</script>

<style>

</style>