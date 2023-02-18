<template>
  <div class="card-sort w-[240px] h-[586px] rounded-[8px]">
    <div
      class="px-[18px] pt-[20px] pb-[18px] font-semibold text-[#E5E5E5] text-base border-b border-white/[.07]"
    >
      Sort Result By
    </div>
    <div class="px-[18px] pt-[11px] pb-[31px] border-b border-white/[.07]">
      <select
        class="sort-select bg-[#E0E0E0]/[.13] text-[#E5E5E5] text-sm rounded-[4px] w-full h-[36px] pl-[17px] pr-[14px]"
      >
        <option v-for="(sorter, index) in sorting" :key="index">
          {{ sorter }}
        </option>
      </select>
    </div>
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
        <input
          type="checkbox"
          class="bg-white/[.2] border border-white/[.5] rounded-[4px] form-checkbox text-[#e74c3c]"
        />
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
const sorting = ref([
  'Popularity Ascending',
  'Popularity Descending',
  'Release Date Ascending',
  'Release Date Descending',
  'Rating Ascending',
  'Rating Descending',
]);
</script>

<style lang="postcss" scoped>
.card-sort {
  background: linear-gradient(180deg, #0e1723 0%, rgba(30, 35, 42, 0) 100%);
}
.sort-select {
  appearance: none;
  background-image: url('~/assets/images/ic_dropdown.svg');
  background-repeat: no-repeat;
  background-position: right 12px center;
}
</style>
