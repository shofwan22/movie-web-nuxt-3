<template>
  <div>
    <div class="w-[220px] h-[330px] relative cursor-pointer group/item">
      <img
        v-if="chooseImage"
        :src="chooseImage"
        width="220"
        height="330"
        alt=""
      />
      <div
        class="absolute top-0 right-0 w-[48px] h-[32px] bg-[#1E232B]/[.8] flex items-center justify-center text-[#E5E5E5] text-lg font-bold"
      >
        {{ rating }}
      </div>
      <div
        class="bg-black/[.8] h-full w-full absolute top-0 py-[78px] text-center group/edit invisible group-hover/item:visible"
      >
        <div class="flex justify-center mb-12">
          <img src="~/assets/images/ic_star.png" alt="" />
          <p class="text-white font-semibold text-2xl ml-2.5">{{ rating }}</p>
        </div>
        <p class="font-semibold text-lg text-white mb-[52px]">Action</p>
        <NuxtLink to="/movies/detail/1" class="flex justify-center">
          <div
            class="rounded-[32px] bg-[#FF0000] uppercase font-bold text-base text-[#E5E5E5] px-[33px] pt-[7px] pb-[8px] w-[107px]"
          >
            View
          </div>
        </NuxtLink>
      </div>
    </div>

    <div class="mt-[13px]">
      <p class="movie-title text-[#E5E5E5] font-semibold text-base mb-[3px]">
        {{ title }}
      </p>
      <p class="movie-subtitle text-[#929292] text-sm font-normal">
        {{ year }}
      </p>
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
  category: {
    type: String,
    default: '',
  },
  title: {
    type: String,
    default: '',
  },
  year: {
    type: String,
    default: '',
  },
});
const allImages = import.meta.glob('~/assets/images/*.png');
const chooseImage = ref('');

onMounted(() => {
  console.log('masuk', allImages[`/assets/images/${props.image}`]);
  allImages[`/assets/images/${props.image}`]().then((mod) => {
    chooseImage.value = mod.default;
  });
});
</script>
