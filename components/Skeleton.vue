<template>
  <div class="back relative overflow-hidden">
    <p class="absolute w-6 blured"></p>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.back {
  background-color: #a8aead;
}
.blured {
  background-color: #fff;
  filter: blur(5px);
  box-shadow: 0 0 10px 0 #fff;
  height: 150%;
  animation: bounce-out 1.2s infinite;
  transform: rotate(10deg) translateY(-25%);
}
@keyframes bounce-out {
  0% {
    left: 0;
  }
  100% {
    left: 100%;
  }
}
</style>
