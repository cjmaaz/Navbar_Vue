<template>
  <div>
    <Sidebar />
    <!--<div :style="{ 'margin-left': sidebarWidth }">-->
    <div :style="{ 'margin-left': '38px' }">
      <router-view />
    </div>
  </div>
</template>

<script>
import Sidebar from "@/components/Sidebar";
import { sidebarWidth } from "@/store/state";
export default {
  components: { Sidebar },
  setup() {
    return { sidebarWidth };
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.7);
  display: none;
  &.show {
    display: block;
  }
}
</style>
