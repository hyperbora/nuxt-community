<template>
  <div class="min-h-screen bg-gray-100 text-gray-900">
    <!-- 상단 네비게이션 -->
    <nav class="bg-white border-b border-gray-200 sticky top-0 z-50">
      <div class="px-4 py-3 flex items-center justify-between">
        <div class="flex items-center">
          <NuxtLink to="/" class="text-xl font-bold text-orange-600">
            NuxtReddit
          </NuxtLink>
        </div>

        <!-- Middle: Search (크기 줄이기: w-full + max-w-md) -->
        <div class="flex justify-center w-full max-w-md px-3">
          <input
            type="text"
            placeholder="검색"
            class="w-full rounded-md border border-gray-300 px-3 py-2 text-sm focus:border-orange-500 focus:ring-orange-500"
          />
        </div>

        <div class="flex justify-end">
          <button
            class="px-4 py-2 rounded-md bg-orange-500 text-white hover:bg-orange-600 text-sm whitespace-nowrap"
          >
            로그인
          </button>
        </div>
      </div>
    </nav>

    <!-- 메인 컨텐츠 -->
    <main class="mx-auto max-w-5xl px-4 py-6">
      <slot />
    </main>
  </div>
</template>
