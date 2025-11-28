<script setup lang="ts">
import { ref } from "vue";
import { Icon } from "@iconify/vue";

const isMenuOpen = ref(false);
function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}
</script>

<template>
  <div class="flex flex-col min-h-screen bg-gray-50 text-gray-800">
    <!-- Header -->
    <header class="border-b bg-white/80 backdrop-blur sticky top-0 z-50">
      <div
        class="max-w-6xl mx-auto flex items-center justify-between px-4 py-3"
      >
        <!-- 로고 -->
        <NuxtLink
          to="/"
          class="font-bold text-xl text-green-600 hover:text-green-700"
        >
          NuxtBoard
        </NuxtLink>

        <!-- 데스크탑 메뉴 -->
        <nav class="hidden md:flex space-x-6 text-sm font-medium">
          <NuxtLink to="/" class="hover:text-green-600">Home</NuxtLink>
          <NuxtLink to="/posts" class="hover:text-green-600">Posts</NuxtLink>
          <NuxtLink to="/about" class="hover:text-green-600">About</NuxtLink>
        </nav>

        <!-- 모바일 메뉴 버튼 -->
        <button
          v-on:click="toggleMenu"
          class="md:hidden p-2 rounded hover:bg-gray-100"
        >
          <Icon icon="mdi:menu" style="font-size: 36px" />
        </button>
      </div>

      <!-- 모바일 메뉴 -->
      <transition name="fade">
        <nav
          v-if="isMenuOpen"
          class="md:hidden bg-white border-t flex flex-col px-4 py-2 space-y-2"
        >
          <NuxtLink
            to="/"
            v-on:click="toggleMenu"
            class="py-2 border-b hover:text-green-600"
          >
            Home
          </NuxtLink>
          <NuxtLink
            to="/posts"
            v-on:click="toggleMenu"
            class="py-2 border-b hover:text-green-600"
          >
            Posts
          </NuxtLink>
          <NuxtLink
            to="/about"
            v-on:click="toggleMenu"
            class="py-2 hover:text-green-600"
          >
            About
          </NuxtLink>
        </nav>
      </transition>
    </header>

    <!-- Main -->
    <main class="flex-1 max-w-6xl mx-auto w-full px-4 py-6">
      <NuxtPage />
    </main>

    <!-- Footer -->
    <AppFooter />
  </div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
