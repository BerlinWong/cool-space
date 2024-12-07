<template>
  <nav
    class="bg-white dark:bg-gray-800 border-b border-gray-200 dark:border-gray-700 transform transition duration-500"
  >
    <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
      <div class="relative flex items-center justify-between h-16">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <button
            type="button"
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
            aria-controls="mobile-menu"
            aria-expanded="false"
          >
            <span class="sr-only">Open main menu</span>
            <!-- Icon when menu is closed. -->
            <svg
              class="block h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16m-7 6h7"
              />
            </svg>
            <!-- Icon when menu is open. -->
            <svg
              class="hidden h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
        <div
          class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start"
        >
          <div class="flex-shrink-0 rounded-md">
            <img
              class="h-8 w-auto rounded-md"
              src="@/assets/logo.png"
              alt="Workflow"
            />
          </div>
          <div class="hidden sm:block sm:ml-6">
            <div class="flex space-x-4">
              <a
                href="/"
                class="text-gray-900 hover:text-gray-700 dark:text-white dark:hover:text-gray-300 px-3 py-2 rounded-md text-sm font-medium"
                >Home</a
              >
              <a
                href="/team"
                class="text-gray-900 hover:text-gray-700 dark:text-white dark:hover:text-gray-300 px-3 py-2 rounded-md text-sm font-medium"
                >Team</a
              >
              <a
                href="#"
                class="text-gray-900 hover:text-gray-700 dark:text-white dark:hover:text-gray-300 px-3 py-2 rounded-md text-sm font-medium"
                >Projects</a
              >
              <a
                href="/about"
                class="text-gray-900 hover:text-gray-700 dark:text-white dark:hover:text-gray-300 px-3 py-2 rounded-md text-sm font-medium"
                >About</a
              >
            </div>
          </div>
        </div>
        <button
          @click="toggleDarkMode"
          class="ml-auto p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
        >
          <span v-if="isDarkMode">🌞</span>
          <span v-else>🌜</span>
        </button>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state. -->
    <div class="sm:hidden" id="mobile-menu">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a
          href="#"
          class="text-gray-900 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Dashboard</a
        >
        <a
          href="#"
          class="text-gray-900 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Team</a
        >
        <a
          href="#"
          class="text-gray-900 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Projects</a
        >
        <a
          href="#"
          class="text-gray-900 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Calendar</a
        >
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";

const isDarkMode = ref(false);

// 在组件挂载时检查 localStorage 中的深色模式状态
onMounted(() => {
  const savedMode = localStorage.getItem("darkMode");
  if (savedMode) {
    isDarkMode.value = savedMode === "true";
    document.documentElement.classList.toggle("dark", isDarkMode.value);
  }
});

function toggleDarkMode() {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.classList.toggle("dark", isDarkMode.value);
  // 将当前的深色模式状态保存到 localStorage
  localStorage.setItem("darkMode", isDarkMode.value.toString());
}
</script>
