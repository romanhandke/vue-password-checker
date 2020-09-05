<template>
  <div class="home">
    <section id="upper">
      <div class="content">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          height="24"
          width="24"
          viewBox="0 0 24 24"
          class="logo"
        >
          <path d="M0 0h24v24H0z" fill="none" />
          <path
            fill="#00AEF9"
            d="M18 8h-1V6c0-2.76-2.24-5-5-5S7 3.24 7 6v2H6c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V10c0-1.1-.9-2-2-2zm-6 9c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zm3.1-9H8.9V6c0-1.71 1.39-3.1 3.1-3.1 1.71 0 3.1 1.39 3.1 3.1v2z"
          />
        </svg>
        <h1 class="title">are you save?</h1>
      </div>
      <svg id="line" viewBox="0 0 100 100" preserveAspectRatio="none">
        <polygon fill="#00AEF9" points="0,100 100,0 100,100" />
      </svg>
    </section>
    <section id="lower">
      <div class="content">
        <button class="btn-primary">make sure</button>
        <button class="btn-secondary">how it works</button>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  components: {}
})
export default class Home extends Vue {}
</script>

<style>
#line {
  position: absolute;
  bottom: -1px;
  width: 100%;
  height: 10vw;
}
#upper {
  background: #ffffff;
  height: 50vh;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}
#lower {
  background: #00aef9;
  height: 50vh;
}
.content {
  text-align: center;
}
.logo {
  height: 120px;
  width: 120px;
}
.title {
  color: #00aef9;
  margin-top: 20px;
  text-transform: uppercase;
}
.btn-primary {
  background: #ffffff;
  border: 2px solid #ffffff;
  border-radius: 8px;
  box-shadow: 0px 4px 0px rgba(0, 0, 0, 0.08);
  color: #00aef9;
  font-size: 1.2em;
  font-weight: bolder;
  padding: 10px;
  text-transform: uppercase;
  width: 100%;
}
.btn-secondary {
  background: #00aef9;
  border: 2px solid #00aef9;
  border-radius: 8px;
  box-shadow: 0px 4px 0px rgba(0, 0, 0, 0.08);
  color: #ffffff;
  font-size: 1.2em;
  margin-top: 20px;
  padding: 10px;
  text-transform: uppercase;
  width: 100%;
}
</style>
