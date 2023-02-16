<template>
  <div
    class="rounded-[14px] w-[582px] h-[284px] bg-[#F9F9F9] shadow-black/10 py-6 px-5"
  >
    <div class="flex items-center justify-between">
      <div class="flex items-center">
        <div
          class="w-[48px] h-[48px] rounded-full mr-[18px] bg-[#1E232B]/[.21]"
        ></div>
        <div>
          <p class="text-sm text-[#1E232A] font-bold mb-[3px]">{{ name }}</p>
          <p class="text-xs text-[#666666] font-normal">{{ date }}</p>
        </div>
      </div>
      <div
        class="h-[52px] w-[97px] bg-[#C4C4C4]/[.28] flex items-center justify-center rounded-[7px]"
      >
        <img src="~/assets/images/ic_star.png" width="17" height="17" alt="" />
        <p class="text-black font-semibold text-4xl ml-[6px]">{{ rating }}</p>
      </div>
    </div>
    <div
      class="mt-[25px] font-normal text-black text-[13px] leading-[150%] italic"
    >
      {{ message }}
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  name: {
    type: String,
    default: '',
  },
  date: {
    type: String,
    default: '',
  },
  rating: {
    type: String,
    default: '',
  },
  message: {
    type: String,
    default: '',
  },
});
</script>
