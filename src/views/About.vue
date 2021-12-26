<template>
  <div>
    <div class="overlay" :class="{ show: !collapsed }"></div>
    <div class="about">
      <h1>This is an about page</h1>
    </div>
  </div>
</template>
<script>
import { collapsed } from "../store/state";

export default {
  setup() {
    return {
      collapsed,
    };
  },
};
</script>
