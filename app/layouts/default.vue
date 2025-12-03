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
          <div
            class="flex items-center w-full bg-white border border-gray-300 rounded-md px-3 py-2 gap-2"
          >
            <span class="text-gray-500 flex items-center">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-4 w-4"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M21 21l-4.35-4.35m0 0A7.5 7.5 0 104.5 4.5a7.5 7.5 0 0012.15 12.15z"
                />
              </svg>
            </span>

            <input
              type="text"
              placeholder="검색"
              class="w-full outline-none text-sm bg-transparent"
            />
          </div>
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
