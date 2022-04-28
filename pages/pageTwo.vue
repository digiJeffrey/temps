<template>
  <div>
    <p>second page</p>
    <digit :number="3" ></digit>
  </div>
</template>

<script>
import Digit from '~/components/digit.vue'

export default {
  components:{Digit}
}
</script>

<style scoped>
div{
  background-color: lightblue;
}

</style>
