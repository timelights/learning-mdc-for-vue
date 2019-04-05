<template>
  <div class="mdc101">
    <header class="mdc-top-app-bar app-bar" id="app-bar">
      <div class="mdc-top-app-bar__row">
        <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
          <a href="#" class="demo-menu material-icons mdc-top-app-bar__navigation-icon">menu</a>
          <span class="mdc-top-app-bar__title">Dismissible Drawer</span>
        </section>
      </div>
    </header>
    <aside class="mdc-drawer mdc-drawer--dismissible mdc-top-app-bar--fixed-adjust">
      <div class="mdc-drawer__content">
        <div class="mdc-list">
          <a class="mdc-list-item mdc-list-item--activated" href="#" aria-current="page">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true">inbox</i>
            <span class="mdc-list-item__text">Inbox</span>
          </a>
          <a class="mdc-list-item" href="#">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true">send</i>
            <span class="mdc-list-item__text">Outgoing</span>
          </a>
          <a class="mdc-list-item" href="#">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true">drafts</i>
            <span class="mdc-list-item__text">Drafts</span>
          </a>
        </div>
      </div>
    </aside>

    <div class="mdc-drawer-app-content mdc-top-app-bar--fixed-adjust">
      <main class="main-content" id="main-content">
        App Content
      </main>
    </div>
  </div>
</template>

<script>
import {MDCDrawer} from "@material/drawer";
import {MDCTopAppBar} from "@material/top-app-bar";

export default {
  data() {
    return {};
  },
  mounted() {
    // instantiate drawer
    const drawer = MDCDrawer.attachTo(document.querySelector('.mdc-drawer'));
    // toggle drawer when clicking on the nav button in the top-app-bar
    const topAppBar = MDCTopAppBar.attachTo(document.getElementById('app-bar'));
    topAppBar.setScrollTarget(document.getElementById('main-content'));
    topAppBar.listen('MDCTopAppBar:nav', () => {
      drawer.open = !drawer.open;
    });
    // Close the drawer when an item is activated in order to dismiss the modal
    // as soon as the user performs an action. Only restore focus to the first
    // focusable element in the main content after the drawer is closed, since
    // it's being closed automatically.
    const listEl = document.querySelector('.mdc-drawer .mdc-list');
    const mainContentEl = document.querySelector('.main-content');

    listEl.addEventListener('click', (event) => {
      drawer.open = false;
    });

    document.body.addEventListener('MDCDrawer:closed', () => {
      mainContentEl.querySelector('input, button').focus();
    });
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/icon?family=Material+Icons");
@import "@material/top-app-bar/mdc-top-app-bar";
@import "@material/drawer/mdc-drawer";
@import "@material/list/mdc-list";

html, body {
  margin: 0;
}

body,
.mdc101 {
  display: flex;
  height: 100vh;
}

.mdc-drawer-app-content {
  flex: auto;
  overflow: auto;
  position: relative;
}

.main-content {
  overflow: auto;
  height: 100%;
}

.app-bar {
  position: absolute;
}

// only apply this style if below top app bar
.mdc-top-app-bar {
  z-index: 7;
}
</style>
