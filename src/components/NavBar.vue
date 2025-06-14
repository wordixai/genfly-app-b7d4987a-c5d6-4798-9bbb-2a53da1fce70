<template>
  <nav class="fixed top-0 w-full z-50 py-4 px-6 md:px-12 transition-all duration-300" 
       :class="{ 'bg-transparent': !scrolled, 'bg-[#050816]/80 backdrop-blur-md': scrolled }">
    <div class="max-w-7xl mx-auto flex justify-between items-center">
      <div class="flex items-center">
        <div class="text-2xl font-bold tech-gradient">DEV<span class="text-white">.TECH</span></div>
      </div>
      
      <!-- Desktop Menu -->
      <div class="hidden md:flex space-x-8">
        <router-link v-for="item in navItems" :key="item.name" :to="item.path" 
                    class="nav-link relative text-sm font-medium tracking-wider uppercase">
          {{ item.name }}
        </router-link>
      </div>
      
      <!-- Mobile Menu Button -->
      <button @click="mobileMenuOpen = !mobileMenuOpen" class="md:hidden text-white">
        <div v-if="!mobileMenuOpen" class="w-6 h-5 flex flex-col justify-between">
          <span class="w-full h-0.5 bg-white"></span>
          <span class="w-full h-0.5 bg-white"></span>
          <span class="w-full h-0.5 bg-white"></span>
        </div>
        <div v-else class="w-6 h-6 relative">
          <span class="absolute top-1/2 left-0 w-full h-0.5 bg-white transform -rotate-45"></span>
          <span class="absolute top-1/2 left-0 w-full h-0.5 bg-white transform rotate-45"></span>
        </div>
      </button>
    </div>
    
    <!-- Mobile Menu -->
    <div v-if="mobileMenuOpen" class="md:hidden absolute top-full left-0 w-full bg-[#050816]/95 backdrop-blur-md py-4 px-6">
      <div class="flex flex-col space-y-4">
        <router-link v-for="item in navItems" :key="item.name" :to="item.path" 
                    @click="mobileMenuOpen = false"
                    class="nav-link text-sm font-medium tracking-wider uppercase py-2">
          {{ item.name }}
        </router-link>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const scrolled = ref(false);
const mobileMenuOpen = ref(false);

const navItems = [
  { name: 'Home', path: '/' },
  { name: 'About', path: '/about' },
  { name: 'Projects', path: '/projects' },
  { name: 'Contact', path: '/contact' }
];

const handleScroll = () => {
  scrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.nav-link {
  color: rgba(255, 255, 255, 0.75);
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover, .router-link-active {
  color: var(--primary);
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, #00f6ff, #915eff);
  transition: width 0.3s ease;
}

.nav-link:hover::after, .router-link-active::after {
  width: 100%;
}
</style>