<template>
  <div class="footer">
    <span class="overlay"></span>
  </div>
</template>

<style scoped>
.footer {
  background-image: url("../assets/security.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  height: 50vh;
  position: relative;
}
.overlay {
  background-color: #00aef9;
  height: 100%;
  left: 0;
  opacity: 0.5;
  position: absolute;
  top: 0;
  width: 100%;
  z-index: 1;
}
</style>
