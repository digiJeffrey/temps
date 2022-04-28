<template>
  <div>
    <div class="clouds-outer">
      <div class="cloud1"></div>
      <div class="cloud2"></div>
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
  background: linear-gradient(180deg, #C0D7EC 0%, #D3E3F2 18.92%, #E7EFF4 62.5%, #F6F7F8 100%);
  overflow: hidden;
  position: relative;
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
  background: url('../assets/cloud1.png');
  background-repeat: repeat-x;
  width: 500%;
  height: 100%;
  animation: slide 300s linear infinite;
}

.cloud2 {
  background: url('../assets/cloud2.png');
  background-repeat: repeat-x;
  width: 500%;
  height: 100%;
  animation: slide 400s linear infinite;
  position: absolute;
  top: 50%;
}
</style>
