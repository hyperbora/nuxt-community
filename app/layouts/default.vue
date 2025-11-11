<script setup lang="ts">
import { ref } from 'vue'
import { Icon } from '@iconify/vue'

const isMenuOpen = ref(false)
function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <div class="flex flex-col min-h-screen bg-gray-50 text-gray-800">
    <!-- Header -->
    <header class="border-b bg-white/80 backdrop-blur sticky top-0 z-50">
      <div class="max-w-6xl mx-auto flex items-center justify-between px-4 py-3">
        <!-- 로고 -->
        <NuxtLink to="/" class="font-bold text-xl text-green-600 hover:text-green-700">
          NuxtBoard
        </NuxtLink>

        <!-- 데스크탑 메뉴 -->
        <nav class="hidden md:flex space-x-6 text-sm font-medium">
          <NuxtLink to="/" class="hover:text-green-600">Home</NuxtLink>
          <NuxtLink to="/posts" class="hover:text-green-600">Posts</NuxtLink>
          <NuxtLink to="/about" class="hover:text-green-600">About</NuxtLink>
        </nav>

        <!-- 모바일 메뉴 버튼 -->
        <button v-on:click="toggleMenu" class="md:hidden p-2 rounded hover:bg-gray-100">
          <Icon icon="mdi:menu" style="font-size: 36px" />
        </button>
      </div>

      <!-- 모바일 메뉴 -->
      <transition name="fade">
        <nav
          v-if="isMenuOpen"
          class="md:hidden bg-white border-t flex flex-col px-4 py-2 space-y-2"
        >
          <NuxtLink to="/" v-on:click="toggleMenu" class="py-2 border-b hover:text-green-600">
            Home
          </NuxtLink>
          <NuxtLink to="/posts" v-on:click="toggleMenu" class="py-2 border-b hover:text-green-600">
            Posts
          </NuxtLink>
          <NuxtLink to="/about" v-on:click="toggleMenu" class="py-2 hover:text-green-600">
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
    <footer class="border-t bg-white dark:bg-gray-900 pt-2 pb-2">
      <div class="sm:flex sm:items-center sm:justify-between pl-2 pr-2">
        <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400">
          © {{ new Date().getFullYear() }}
          <a href="#" class="hover:underline">NuxtBoard.</a>
          All Rights Reserved.
        </span>
        <div class="flex mt-4 sm:justify-center sm:mt-0">
          <a
            href="https://github.com/hyperbora/nuxt-community"
            class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
          >
            <svg
              class="w-4 h-4"
              aria-hidden="true"
              xmlns="http://www.w3.org/2000/svg"
              fill="currentColor"
              viewBox="0 0 20 20"
            >
              <path
                fill-rule="evenodd"
                d="M10 .333A9.911 9.911 0 0 0 6.866 19.65c.5.092.678-.215.678-.477 0-.237-.01-1.017-.014-1.845-2.757.6-3.338-1.169-3.338-1.169a2.627 2.627 0 0 0-1.1-1.451c-.9-.615.07-.6.07-.6a2.084 2.084 0 0 1 1.518 1.021 2.11 2.11 0 0 0 2.884.823c.044-.503.268-.973.63-1.325-2.2-.25-4.516-1.1-4.516-4.9A3.832 3.832 0 0 1 4.7 7.068a3.56 3.56 0 0 1 .095-2.623s.832-.266 2.726 1.016a9.409 9.409 0 0 1 4.962 0c1.89-1.282 2.717-1.016 2.717-1.016.366.83.402 1.768.1 2.623a3.827 3.827 0 0 1 1.02 2.659c0 3.807-2.319 4.644-4.525 4.889a2.366 2.366 0 0 1 .673 1.834c0 1.326-.012 2.394-.012 2.72 0 .263.18.572.681.475A9.911 9.911 0 0 0 10 .333Z"
                clip-rule="evenodd"
              />
            </svg>
            <span class="sr-only">GitHub account</span>
          </a>
        </div>
      </div>
    </footer>
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
