<template>
  <div class="flex">
    <div
      class="bg-[#FF0000] px-4 pt-1.5 pb-[9px] text-sm text-[#E5E5E5] rounded-[36px] cursor-pointer"
    >
      {{ menuOne }}
    </div>
    <div
      class="bg-black/[.2] px-4 pt-1.5 pb-[9px] text-sm text-[#E5E5E5] rounded-[36px] cursor-pointer ml-[21px]"
    >
      {{ menuTwo }}
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  menuOne: {
    type: String,
    default: '',
  },
  menuTwo: {
    type: String,
    default: '',
  },
});
</script>
