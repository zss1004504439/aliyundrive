<template>
  <div class="container">
    <aside>
      <Head></Head>
      <Nav @onClick="onNavItemClick"></Nav>
      <Foot></Foot>
      <Profile></Profile>
    </aside>
    <main>
      <header>
        <slot name="header"></slot>
      </header>
      <section class="main-head">
        <FilePath></FilePath>
        <FileActions></FileActions>
      </section>
      <section class="main-tips"></section>
      <FileFolder />
      <section class="foot"></section>
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Head from "./components/Head.vue";
import Nav from "./components/Nav.vue";
import Profile from "./components/Profile.vue";
import FilePath from "./components/main/FilePath.vue";
import FileFolder from "./components/main/FileFolder.vue";

import FileActions from "./components/main/FileActions.vue";
import { INavItem } from "./Drive";

export default defineComponent({
  components: {
    Head,
    Nav,
    Profile,
    FilePath,
    FileFolder,
    FileActions,
  },
  setup(props, ctx) {
    return {};
  },
  methods: {
    onNavItemClick(item: INavItem) {
      console.log("🚀 onNavItemClick", item);
    },
  },
});
</script>

<style scoped>
.container {
  height: 100%;
  height: 100vh;
  display: flex;
}
aside {
  display: flex;
  position: relative;
  flex-direction: column;
  height: 100%;
  width: 240px;
  background-color: rgba(132, 133, 141, 0.08);
}
main {
  flex: 1;
  position: relative;
padding-top: 28px;
}
.main-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
  height: 40px;
  padding: 0 40px;
}
</style>