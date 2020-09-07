<template>
  <div class="password-checker">
    <Header />
    <div class="content">
      <div class="loading" v-if="loading">
        <LoadingSpinner />
      </div>
      <form v-if="showPrompt">
        <label for="password" class="sr-only">Enter your password</label>
        <input
          name="password"
          type="password"
          class="input"
          placeholder="Enter your password"
          tabindex="1"
        />
        <input
          type="button"
          value="check password"
          class="button"
          @click="checkPassword()"
        />
      </form>
      <div
        class="password-not-leaked"
        v-if="!passwordLeaked && !showPrompt && !loading"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          height="24"
          viewBox="0 0 24 24"
          width="24"
          class="okay"
        >
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path
            d="M1 21h4V9H1v12zm22-11c0-1.1-.9-2-2-2h-6.31l.95-4.57.03-.32c0-.41-.17-.79-.44-1.06L14.17 1 7.59 7.59C7.22 7.95 7 8.45 7 9v10c0 1.1.9 2 2 2h9c.83 0 1.54-.5 1.84-1.22l3.02-7.05c.09-.23.14-.47.14-.73v-2z"
            fill="#51ec51"
          />
        </svg>
      </div>
      <div
        class="password-leaked"
        v-if="passwordLeaked && !showPrompt && !loading"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          height="24"
          viewBox="0 0 24 24"
          width="24"
          class="warning"
        >
          <path d="M0 0h24v24H0z" fill="none" />
          <path
            d="M1 21h22L12 2 1 21zm12-3h-2v-2h2v2zm0-4h-2v-4h2v4z"
            fill="#f43838"
          />
        </svg>
        <p>Please change your password</p>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import { Component, Vue } from "vue-property-decorator";
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import LoadingSpinner from "../components/LoadingSpinner.vue";

@Component({
  components: {
    Header,
    Footer,
    LoadingSpinner
  }
})
export default class PasswordChecker extends Vue {
  loading = false;
  passwordLeaked = false;
  showPrompt = true;

  checkPassword() {
    this.loading = true;
    this.showPrompt = false;
    setTimeout(() => {
      this.loading = false;
      this.passwordLeaked = false;
    }, 3000);
  }
}
</script>

<style scoped>
.content {
  align-items: center;
  background-color: #ededed;
  display: flex;
  flex-direction: column;
  height: 40vh;
  justify-content: center;
}
form {
  width: 80%;
}
.input {
  border: 2px solid #00aef9;
  border-radius: 8px;
  color: #00aef9;
  cursor: none;
  outline: none;
  padding: 10px;
  text-align: center;
  text-transform: uppercase;
  width: 100%;
}
.input::placeholder {
  color: #00aef9;
  font-weight: bold;
}
.button {
  padding: 10px;
  width: 100%;
  background: #00aef9;
  outline: none;
  border: 2px solid #00aef9;
  border-radius: 8px;
  margin-top: 20px;
  color: white;
  text-transform: uppercase;
  font-weight: bold;
}
.sr-only {
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  height: 1px;
  width: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
}
.password-leaked,
.password-not-leaked {
  text-align: center;
}
.warning,
.okay {
  width: 120px;
  height: 120px;
}
p {
  font-size: 1.2em;
  color: #f43838;
}
</style>
