<template>
  <button :class="classList" @click="redirect()">{{ text }}</button>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({
  components: {}
})
export default class Button extends Vue {
  @Prop({ required: false }) readonly route!: string | null;
  @Prop({ type: String, required: true }) readonly classList!: string;
  @Prop({ type: String, required: true }) readonly text!: string;

  redirect() {
    if (this.route === null) {
      return;
    }

    this.$router.push(this.route);
  }
}
</script>

<style scoped>
button {
  cursor: pointer;
}
.primary {
  background: #ffffff;
  border: 2px solid #ffffff;
  border-radius: 8px;
  box-shadow: 0px 4px 0px rgba(0, 0, 0, 0.08);
  color: #00aef9;
  font-size: 1.2em;
  font-weight: bolder;
  margin: 10px 0;
  outline: none;
  padding: 10px;
  text-transform: uppercase;
  width: 100%;
}
.secondary {
  background: #00aef9;
  border: 1px solid #ffffff;
  border-radius: 8px;
  box-shadow: 0px 4px 0px rgba(0, 0, 0, 0.08);
  color: #ffffff;
  font-size: 1.2em;
  margin: 10px 0;
  outline: none;
  padding: 10px;
  text-transform: uppercase;
  width: 100%;
}
</style>
