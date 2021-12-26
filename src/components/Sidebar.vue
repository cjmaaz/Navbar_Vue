<template>
  <div class="sidebar" :style="{ width: sidebarWidth }" @click.self="toggleSidebar">
    <h1>
      <span v-if="collapsed">
        <i class="fas fa-door-open"></i>
      </span>
      <span v-else>Pent House</span>
    </h1>

    <SidebarLink to="/" icon="fas fa-home">Home</SidebarLink>
    <SidebarLink to="/dashboard" icon="fas fa-atom">Toggle</SidebarLink>
    <SidebarLink to="/about" icon="fas fa-user-circle">About</SidebarLink>

    <span
      class="collapse-icon"
      :class="{ 'rotate-180': collapsed }"
      @click.stop="toggleSidebar"
    >
      <i class="fas fa-angle-double-left" />
    </span>
  </div>
</template>

<script>
import SidebarLink from './SidebarLink'
import { collapsed, toggleSidebar, sidebarWidth } from '@/store/state'
export default {
  props: {},
  components: { SidebarLink },
  setup() {
    return { collapsed, toggleSidebar, sidebarWidth }
  }
}
</script>

<style>
:root {
  --sidebar-bg-color: hsl(0, 0%, 0%);
  --sidebar-item-hover: hsl(0, 0%, 30%);
  --sidebar-item-active: hsl(0, 0%, 30%);
}
</style>

<style scoped>
.sidebar {
  color: white;
  background-color: var(--sidebar-bg-color);
  float: left;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  bottom: 0;
  padding: 0.5em;
  transition: 0.3s ease;
  display: flex;
  flex-direction: column;
}
.sidebar h1 {
  height: 1.5em;
}
.collapse-icon {
  position: absolute;
  bottom: 0;
  padding: 0.75em;
  color: rgba(255, 255, 255, 0.7);
  transition: 0.2s linear;
}
.rotate-180 {
  transform: rotate(180deg);
  transition: 0.2s linear;
}
</style>