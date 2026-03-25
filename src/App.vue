<script setup lang="ts">
import { ref, onMounted } from 'vue'
import AppNavbar from '@/vue/components/AppNavbar.vue'

const isVisible = ref(false)

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true
  }, 100)
})
</script>

<template>
  <div :class="{ 'navbar-container': true, 'animate-in': isVisible }">
    <AppNavbar />
  </div>
  <router-view />
</template>

<style>
.navbar-container {
  position: relative;
  transform: translateY(-100%);
  transition: transform 0.8s ease-out;
}

.navbar-container.animate-in {
  transform: translateY(0);
}
</style>
