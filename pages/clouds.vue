<template>
  <div>
    <div class="clouds-outer">
      <div class="cloud1"></div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.clouds-outer {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

@keyframes slide {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%); /* The image width */
  }
}

.cloud1 {
  /* background: url('../assets/shutterstock_429042058 1.png'); */
  background-repeat: repeat-x;
  width: 500%;
  height: 100%;
  animation: slide 20s linear infinite;
}
</style>
