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
        <Button text="make sure" route="/check" classList="primary" />
        <Button text="how it works" route="/about" classList="secondary" />
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Button from "../components/Button.vue";

@Component({
  components: {
    Button
  }
})
export default class Home extends Vue {
  redirect(route: string) {
    this.$router.push(route);
  }
}
</script>

<style scoped>
#line {
  position: absolute;
  bottom: -1px;
  width: 100%;
  height: 10vw;
}
#upper {
  align-items: center;
  background: #ffffff;
  display: flex;
  height: 50vh;
  justify-content: center;
  position: relative;
}
#lower {
  align-items: center;
  background: #00aef9;
  display: flex;
  height: 50vh;
  justify-content: center;
  position: relative;
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
@media (min-width: 450px) {
  .home {
    height: 100%;
  }
  #upper {
    height: 50%;
  }
  #lower {
    height: 50%;
  }
}
</style>
