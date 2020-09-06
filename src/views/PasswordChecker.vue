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
      <div class="password-not-leaked" v-if="!passwordLeaked && !showPrompt">
        <h1>NOT LEAKED</h1>
      </div>
      <div class="password-leaked" v-if="passwordLeaked && !showPrompt">
        <h1>LEAKED</h1>
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
      this.passwordLeaked = true;
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
</style>
