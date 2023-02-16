<template>
  <div class="card-sort w-[240px] h-[586px] rounded-[8px]">
    <div
      class="px-[18px] pt-[20px] pb-[18px] font-semibold text-[#E5E5E5] text-base border-b border-white/[.07]"
    >
      Sort Result By
    </div>
    <div
      class="px-[18px] pt-[11px] pb-[31px] border-b border-white/[.07]"
    ></div>
    <div
      class="px-[18px] pt-[11px] pb-[13px] font-semibold text-[#E5E5E5] text-base border-b border-white/[.07]"
    >
      Genres
    </div>
    <div class="px-[18px] pt-[18px]">
      <div
        v-for="(category, index) in categories"
        :key="index"
        class="flex items-center justify-between mb-3"
      >
        <p class="text-white text-sm font-normal">{{ category }}</p>
        <input type="checkbox" class="sort-checbox" />
      </div>
    </div>
  </div>
</template>

<script setup>
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
.card-sort {
  background: linear-gradient(180deg, #0e1723 0%, rgba(30, 35, 42, 0) 100%);
}
.sort-checbox {
  accent-color: #e74c3c;
}
</style>
