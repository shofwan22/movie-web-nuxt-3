<template>
  <div class="title-section">
    <div class="border-section bg-[#E74C3C] w-[112px] h-[6px] mb-3"></div>
    <p :class="`text-[#E5E5E5] ${textSize} font-semibold capitalize`">
      {{ title }}
    </p>
  </div>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: '',
  },
  textSize: {
    type: String,
    default: 'text-[24px]',
  },
});
</script>
