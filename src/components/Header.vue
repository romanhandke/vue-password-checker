<template>
  <div class="header">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      height="24"
      width="24"
      viewBox="0 0 24 24"
      class="logo-small"
    >
      <path d="M0 0h24v24H0z" fill="none" />
      <path
        fill="#00AEF9"
        d="M18 8h-1V6c0-2.76-2.24-5-5-5S7 3.24 7 6v2H6c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V10c0-1.1-.9-2-2-2zm-6 9c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zm3.1-9H8.9V6c0-1.71 1.39-3.1 3.1-3.1 1.71 0 3.1 1.39 3.1 3.1v2z"
      />
    </svg>
    <h2 class="title" @click="redirect('/')">Password Checker</h2>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  components: {}
})
export default class Header extends Vue {
  redirect(route: string) {
    this.$router.push(route);
  }
}
</script>

<style scoped>
.logo-small {
  width: 48px;
  height: 48px;
}
.title {
  color: #00aef9;
}
.header {
  height: 10vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
