<template>
  <div class="flex">
    <NuxtLink to="/movies/detail/1">
      <img :src="image" width="243.08" height="364.61" alt="movie carousel" />
    </NuxtLink>
    <div
      class="bg-black pt-[26px] pl-[25px] pr-[21px] w-[298px] h-[324px] mt-[20px]"
    >
      <div class="flex items-center">
        <img
          src="~/assets/images/ic_star.png"
          class="w-[16.21px] h-[16.21px]"
          alt=""
        />
        <p class="font-bold text-white text-[18px] ml-[5px]">{{ rating }}</p>
      </div>
      <div class="text-white font-medium text-[28px] mt-1 capitalize">
        {{ title }}
      </div>
      <div class="mt-[11px] flex items-center">
        <p class="font-normal text-white text-[16px]">{{ year }}</p>
        <div
          class="w-[6.48px] h-[6.48px] mx-[5px] rounded-full bg-white/[.5]"
        ></div>
        <p class="font-normal text-white text-[16px]">{{ category }}</p>
      </div>
      <div class="mt-[11px] font-normal text-white text-[12px]">
        {{ description }}
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  image: {
    type: String,
    default: '',
  },
  rating: {
    type: String,
    default: '',
  },
  title: {
    type: String,
    default: '',
  },
  category: {
    type: String,
    default: '',
  },
  year: {
    type: String,
    default: '',
  },
  description: {
    type: String,
    default: '',
  },
});
</script>
