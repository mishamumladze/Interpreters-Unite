<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { Camera } from '@lucide/vue'

interface NavItem {
  name: string
  path: string
}

const navItems: NavItem[] = [
  { name: 'Home', path: '/' },
  { name: 'Tools', path: '/tools' },
  { name: 'About', path: '/about' },
]
</script>

<template>
  <!-- Desktop Navbar -->
  <nav class="hidden navbar flex justify-between items-center py-4 px-8 bg-gray text-white">
    <div>Interpreters Unite</div>
    <ul class="flex gap-3 list-none m-0 p-0">
      <li v-for="item in navItems" :key="item.path">
        <RouterLink
          :to="item.path"
          class="transition-all text-shadow-none duration-200 hover:text-shadow-emerald-300 hover:text-shadow-[0_0_20px]"
          exact-active-class="text-emerald-500 font-semibold"
        >
          {{ item.name }}
        </RouterLink>
      </li>
    </ul>
  </nav>
  <!-- Mobile Navbar -->
  <nav class="flex justify-between items-center border-solid border-gray-700 border-t absolute bottom-0 w-full py-5 px-4">
    <div>Interpreters Unite</div>
    <div>
      <button class="border border-solid rounded">
        <Camera/>
      </button>
    </div>
  </nav>
</template>
