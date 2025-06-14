<template>
  <div class="app-container">
    <NavBar />
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
    <ParticlesBackground />
  </div>
</template>

<script setup lang="ts">
import NavBar from './components/NavBar.vue';
import ParticlesBackground from './components/ParticlesBackground.vue';
</script>

<style>
.app-container {
  min-height: 100vh;
  position: relative;
  overflow-x: hidden;
  background-color: #050816;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>