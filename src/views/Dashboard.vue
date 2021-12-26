<template>
  <div>
    <div class="overlay" :class="{ show: !collapsed }"></div>
    <div>
      <h1>The sidebar is {{ collapsed ? "closed" : "open" }}</h1>
      <button @click="toggleSidebar">Toggle Sidebar</button>
    </div>
  </div>
</template>

<script>
import { collapsed, toggleSidebar } from "@/store/state";
export default {
  setup() {
    return { collapsed, toggleSidebar };
  },
};
</script>
