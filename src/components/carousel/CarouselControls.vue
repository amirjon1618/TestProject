<template>
  <!-- in vue 2.x you need wrap these buttons in a div -->
  <button class="carousel-control left" @click="$emit('prev')"><img src="../../../public/left-arrow.svg" alt="Arrow"></button>
  <button class="carousel-control right" @click="$emit('next')"><img src="../../../public/right-arrow.svg" alt="Arrow"></button>
</template>

<script>
export default {
  emits: ["prev", "next"], // vue v3
};
</script>
<style scoped>
.carousel-control {
  border: none;
  display: inline-block;
  position: absolute;
  height: 50px;
  width: 34px;
  top: calc(50% - 25px);
  color: #f3f3f3;
  cursor: pointer;
}
.carousel-control:hover {
  background-color: rgba(0, 0, 0, 0.5);
  border: none;
  display: inline-block;
  position: absolute;
  height: 50px;
  width: 34px;
  top: calc(50% - 25px);
  color: #f3f3f3;
  cursor: pointer;
}
.left {
  left: 0;
}
.right {
  right: 0;
}
</style>
