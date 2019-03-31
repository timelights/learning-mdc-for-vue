<template>
  <div class="mdc101">
    <header class="mdc-top-app-bar mdc-top-app-bar--fixed">
      <div class="mdc-top-app-bar__row">
        <section
          class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start"
        >
          <a class="material-icons mdc-top-app-bar__navigation-icon">menu</a>
          <span class="mdc-top-app-bar__title">Title</span>
        </section>
      </div>
    </header>

    <aside class="mdc-drawer mdc-top-app-bar--fixed-adjust">
      <div class="mdc-drawer__content">
        <nav class="mdc-list">
          <a
            class="mdc-list-item mdc-list-item--activated"
            href="#"
            aria-current="page"
          >
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true"
              >inbox</i
            >
            <span class="mdc-list-item__text">Inbox</span>
          </a>
          <a class="mdc-list-item" href="#">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true"
              >send</i
            >
            <span class="mdc-list-item__text">Outgoing</span>
          </a>
          <a class="mdc-list-item" href="#">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true"
              >drafts</i
            >
            <span class="mdc-list-item__text">Drafts</span>
          </a>
        </nav>
      </div>
    </aside>

    <main>
      <h1>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Assumenda
        inventore libero unde eveniet! Perspiciatis sit sint modi omnis ea
        libero vero, officia ut harum dolore beatae voluptatum. Dolor, sint
        laborum?
      </h1>
      <h1>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Assumenda
        inventore libero unde eveniet! Perspiciatis sit sint modi omnis ea
        libero vero, officia ut harum dolore beatae voluptatum. Dolor, sint
        laborum?
      </h1>
      <h1>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Assumenda
        inventore libero unde eveniet! Perspiciatis sit sint modi omnis ea
        libero vero, officia ut harum dolore beatae voluptatum. Dolor, sint
        laborum?
      </h1>
      <h1>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Assumenda
        inventore libero unde eveniet! Perspiciatis sit sint modi omnis ea
        libero vero, officia ut harum dolore beatae voluptatum. Dolor, sint
        laborum?
      </h1>
      <h1>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Assumenda
        inventore libero unde eveniet! Perspiciatis sit sint modi omnis ea
        libero vero, officia ut harum dolore beatae voluptatum. Dolor, sint
        laborum?
      </h1>
    </main>

    <!-- <div class="mdc-layout-grid">
        <div class="mdc-layout-grid__inner">
            <div class="mdc-layout-grid__cell mdc-layout-grid__cell--span-12">
                <router-link to="/test">ABC</router-link>
                <router-view/>
            </div>
            <div class="mdc-layout-grid__cell">DEF</div>
            <div class="mdc-layout-grid__cell">GHI</div>
        </div>
        </div> -->
  </div>
</template>

<script>
import { MDCList } from "@material/list";
import { MDCDrawer } from "@material/drawer";

export default {
  data() {
    return {};
  },
  mounted() {
    const list = MDCList.attachTo(document.querySelector(".mdc-list"));
    list.wrapFocus = true;
    const drawer = MDCDrawer.attachTo(document.querySelector(".mdc-drawer"));
  }
};
</script>

<style lang="scss">
@import "@material/top-app-bar/mdc-top-app-bar";
@import "@material/layout-grid/mdc-layout-grid";
@import "@material/drawer/mdc-drawer";
@import "@material/list/mdc-list";
</style>
