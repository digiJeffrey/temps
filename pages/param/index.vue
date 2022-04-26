<template>
  <div>
    <div v-for="num in nums" :key="num">
      <nuxt-link :to="`/param/${num}`">{{ num }}</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nums: [1, 2, 3, 4, 5],
      layout: 'noNav',
    }
  },
}
</script>

<style></style>
