<template>
  <div
    class="h-[66px] bg-white/[.05] flex items-center px-20 fixed z-20 w-full"
  >
    <NuxtLink to="/">
      <img src="~/assets/images/MoovieTime-Logo.svg" alt="logo" />
    </NuxtLink>
    <BaseInputSearch />
    <div class="flex items-center h-full">
      <NuxtLink
        class="ml-12 uppercase text-[#E5E5E5] font-semibold flex items-center cursor-pointer relative dropdown h-full"
      >
        <img src="~/assets/images/ic_grid.svg" alt="grid icon" class="mr-3.5" />
        Categories
        <div class="dropdown-content bg-white text-[#1E232B] text-xs">
          <ul>
            <li
              v-for="(category, index) in categories"
              :key="index"
              class="px-3 py-2 hover:bg-slate-100"
            >
              {{ category }}
            </li>
          </ul>
        </div>
      </NuxtLink>
      <NuxtLink
        v-for="(menu, index) in menus"
        :key="index"
        :to="menu.to"
        class="ml-12 uppercase text-[#E5E5E5] font-semibold"
        >{{ menu.title }}</NuxtLink
      >
    </div>
  </div>
</template>

<script setup>
const menus = ref([
  {
    to: '/movies',
    title: 'Movies',
  },
  {
    to: '/movies',
    title: 'TV Shows',
  },
  {
    to: '/movies',
    title: 'Login',
  },
]);
const categories = ref([
  'Action',
  'Advanture',
  'Animation',
  'Comedy',
  'Crime',
  'Documentary',
  'Drama',
  'Family',
  'Fantasy',
  'History',
  'Horror',
]);
</script>

<style lang="postcss" scoped>
.dropdown-content {
  display: none;
  position: absolute;
  min-width: 160px;
  z-index: 1;
  top: 66px;
}

.dropdown:hover .dropdown-content {
  display: block;
}
</style>
