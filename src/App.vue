<script setup>
import Header from './components/Header.vue';
import Sidebar from './components/Sidebar.vue';

</script>

<template>
  <Header />

  <div class="relative" id="main-section">
    <router-view v-slot="{ Component }">
      <div
        class="relative overflow-hidden flex-1 max-w-[800px] m-auto bg-background border-paragraph border border-t-0">
        <keep-alive include="HomeView" :max="3">
          <component :is="Component" />
        </keep-alive>
        <img src="@/assets/doodad.png" alt="pattern" class="border-t border-paragraph mt-5 h-12 w-full object-cover">
      </div>
    </router-view>
  </div>

  <Teleport to="#main-section">
    <sidebar />
  </Teleport>

</template>

<style scoped>

</style>
