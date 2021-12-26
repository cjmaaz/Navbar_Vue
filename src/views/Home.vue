<template>
  <div>
    <div class="overlay" :class="{ show: !collapsed }"></div>
    <div class="home">
      <h1>Home</h1>
    </div>
  </div>
</template>

<script>
import { collapsed } from "../store/state";
export default {
  name: "Home",
  setup() {
    return { collapsed };
  },
};
</script>
