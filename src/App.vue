<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
const routes = [
  {
    path: '/',
    name: 'Home',
  },
  {
    path: '/about',
    name: 'About',
  },
]
</script>

<template>
  <main class="flex h-screen">
    <div class="w-36 h-full bg-gradient-to-b from-gray-800 to-gray-900 text-white shadow-lg">
      <div class="p-4">
        <h1 class="text-lg font-bold mb-4">Components</h1>
      </div>
      <nav class="px-2">
        <div v-for="route in routes" :key="route.path" class="mb-2">
          <RouterLink
            :to="route.path"
            class="block py-2 px-3 rounded-lg transition-colors duration-200 hover:bg-gray-700"
            active-class="bg-gray-700"
          >
            <div class="flex items-center">
              <span
                class="ml-1 font-semibold text-white hover:text-blue-200 transition-all duration-300 drop-shadow-sm"
                >{{ route.name }}</span
              >
            </div>
          </RouterLink>
        </div>
      </nav>
    </div>
    <nav class="w-fit flex flex-col gap-4 p-4">
      <div v-for="route in routes" :key="route.path" class="w-full">
        <RouterLink :to="route.path">{{ route.name }}</RouterLink>
      </div>
    </nav>
    <RouterView />
  </main>
</template>
