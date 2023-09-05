<script setup>
import { ref } from 'vue'

import LayoutHeader from '@/components/layout/Header.vue'
import LayoutSidebar from '@/components/layout/Sidebar.vue'

const isOpenMenu = ref(false);

const toggleMenu = () => {
  isOpenMenu.value = !isOpenMenu.value;
}

</script>

<template>
  <div class="container">
    <div class="sidebar-toggle" @click="toggleMenu">&#5125;</div>
    <layout-header />
    <!-- Создание props Vue -->
    <layout-sidebar :openSidebar="isOpenMenu" />
    <div :class="['content', { content_full: !isOpenMenu }]">
      <router-view />
    </div>
  </div>
</template>

<style lang="scss">
.content {
  max-width: 1400px;
  margin-left: 250px;
  padding: 30px;
  transition: .3s ease;

  &_full {
    margin-left: 0;
  }
}

.sidebar-toggle {
  position: fixed;
  left: 0;
  width: 15px;
  background: var(--primary);
  height: 100%;
  top: 62px;
  z-index: 1;
  cursor: pointer;
  color: #FFF;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media screen and (max-width: 1100px) {
  .content {
    margin-left: 0;
  }
}
</style>