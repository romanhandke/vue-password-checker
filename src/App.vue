<template>
  <div id="app">
    <transition name="slide-fade">
      <router-view />
    </transition>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background-color: #ededed;
}
@media (min-width: 450px) {
  #app {
    border: 2px solid #00aef9;
    border-radius: 4px;
    height: 900px;
    margin: auto;
    margin-top: 10px;
    max-width: 450px;
  }
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter,
.slide-fade-leave-to {
  transform: translateX(-20px);
  opacity: 0;
}
</style>
