<template>
  <div class="about">
    <Header />
    <div class="content-wrapper">
      <div class="content">
        <div class="text-wrapper">
          <h3>how does it work</h3>
          To check whether or not a password has been leaked in a known breach
          this app uses the excelent API of
          <a
            class="link"
            href="https://haveibeenpwned.com/API/v2#SearchingPwnedPasswordsByRange"
            >haveibeenpwned.com</a
          >
        </div>
        <div class="text-wrapper">
          <h3>Two important things</h3>
          <ol>
            <li>The password never leaves the mashine</li>
            <li>Not even haveibeenpwned.com will know the password</li>
          </ol>
        </div>
        <div class="text-wrapper">
          <h3>How is that possible?</h3>
          <ol>
            <li>The password is hashed with SHA1</li>
            <li>
              The first five characters of the hash are sent to the API as a
              string
            </li>
            <li>
              The api answers with all hashes of passwords that start with that
              string
            </li>
            <li>
              If the list of hashes contains ours it is time to change the
              password
            </li>
          </ol>
        </div>
        <Button text="check password" classList="secondary" route="/check" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Header from "../components/Header.vue";
import Button from "../components/Button.vue";

@Component({
  components: {
    Header,
    Button
  }
})
export default class About extends Vue {
  messageTop = `
        This app uses the haveibeenpwned API to check whether or not a password has been leaked in a known breach.
      `;
  messageBottom = `It is important to note that the password neither travels through the internet nor does it become know to haveibeenpwned. Once the password is entered it will be hashed via SHA1 and only the first 5 characters of that hash will be sent to the API. Upon receiving the characters the API will send back hashes of passwords known to have been leaked and start with the received string.
  Back in the browser this will be checked to see whether or nor it contains the password. So at no point does the password leave the mashine the app is being run on.`;
}
</script>

<style scoped>
.content {
  font-size: 1.1em;
  height: 100%;
  margin: auto;
  width: 90%;
}
h3 {
  text-transform: uppercase;
  color: #00aef9;
  padding-bottom: 3px;
}
a {
  text-decoration: none;
}
a,
a:visited {
  color: #00aef9;
}
ol {
  padding-left: 19px;
}
.text-wrapper {
  margin-top: 30px;
  line-height: 1.5em;
}
.secondary {
  margin-top: 20px;
}
</style>
