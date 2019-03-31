<template>
  <div id="app">
    <MDC101 />
  </div>
</template>

<script>
import MDC101 from "@/components/MDC101.vue";
import { MDCRipple } from "@material/ripple";
import { MDCTextField } from "@material/textfield";
import { MDCTopAppBar } from "@material/top-app-bar/index";

export default {
  components: {
    MDC101
  },
  mounted() {
    // intanstiate the buttons with ripple
    const buttons = document.querySelectorAll(".add-ripple");
    for (let i = 0; i < buttons.length; i++) {
      new MDCRipple(buttons[i]);
    }
    // instantiate textfields
    const textfields = document.querySelectorAll(".mdc-text-field");
    for (let i = 0; i < textfields.length; i++) {
      new MDCTextField(textfields[i]);
    }
    const topAppBarElement = document.querySelector(".mdc-top-app-bar");
    const topAppBar = new MDCTopAppBar(topAppBarElement);
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Roboto:300,400,500,700");
@import url("https://fonts.googleapis.com/icon?family=Material+Icons");
@import "@material/button/mdc-button";

html,
body {
  font-family: "Roboto", "Helvetica", "Arial";
  padding: 0;
  margin: 0;
}
</style>
