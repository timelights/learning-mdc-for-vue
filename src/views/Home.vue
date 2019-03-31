<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <button class="mdc-button mdc-button--raised add-ripple">Button</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import { MDCRipple } from "@material/ripple";

export default {
  name: "home",
  components: {
    HelloWorld
  },
  mounted() {
    // intanstiate the buttons with ripple
    const buttons = document.querySelectorAll(".add-ripple");
    for (let i = 0; i < buttons.length; i++) {
      new MDCRipple(buttons[i]);
    }
  }
};
</script>
