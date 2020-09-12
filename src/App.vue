<template>
  <div id="app">
    <router-view />
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
</style>
