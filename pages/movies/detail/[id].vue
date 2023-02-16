<template>
  <div>
    <div
      class="section-hero h-[469px] bg-[url('~/assets/images/bg-wonder.png')] pt-[252px] relative"
    >
      <div
        class="absolute bottom-0 h-[80px] bg-black/[.5] w-full pl-[328px] flex items-center"
      >
        <img src="~/assets/images/ic_star.png" alt="" />
        <p class="text-4xl font-semibold text-[#E5E5E5] ml-[17px]">7.0</p>
        <div class="flex">
          <div
            v-for="(detail, index) in detailMovie"
            :key="index"
            :class="[
              index < detailMovie.length - 1
                ? 'border-r border-r-white/[.5]'
                : '',
              'px-[33px]',
            ]"
          >
            <p class="uppercase text-white/[.5] text-xs font-medium mb-[3px]">
              {{ detail.title }}
            </p>
            <p class="text-white font-medium text-xs uppercase">
              {{ detail.info }}
            </p>
          </div>
        </div>
      </div>
      <div class="px-20 z-10 relative flex">
        <img
          src="~/assets/images/movie-wonder.png"
          width="220"
          height="330"
          alt=""
        />
        <div class="ml-[33px] text-white pt-4 flex flex-col justify-between">
          <div>
            <p class="font-medium text-lg">2020</p>
            <h2 class="font-semibold text-4xl text-[#E5E5E5] mt-px">
              Wonder Woman 1984
            </h2>
            <p class="font-medium text-sm mt-1">Fantasy, Action, Adventure</p>
          </div>
          <div class="w-[526px]">
            <p class="font-semibold text-[#FF0000] text-sm uppercase mb-[9px]">
              overview
            </p>
            <p class="text-black text-sm leading-[200%]">
              Wonder Woman comes into conflict with the Soviet Union during the
              Cold War in the 1980s and finds a formidable foe by the name of
              the Cheetah.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="bg-white h-[1440px] px-20"></div>
    <div class="h-[537px] px-20 py-[50px]">
      <p class="text-base font-semibold text-white uppercase">
        Recommended Movies
      </p>
      <div class="mt-[37px]">
        <div class="mt-[43px] grid grid-cols-5 gap-x-1 gap-y-9">
          <BaseCardMovie
            v-for="(movie, index) in listMovie"
            :key="index"
            :image="movie.image"
            :rating="movie.rating"
            :category="movie.category"
            :title="movie.title"
            :year="movie.year"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const detailMovie = ref([
  {
    title: 'User Score',
    info: '3621 Votes',
  },
  {
    title: 'Status',
    info: 'Released',
  },
  {
    title: 'language',
    info: 'english',
  },
  {
    title: 'budget',
    info: '$200,000,000.00',
  },
  {
    title: 'production',
    info: 'DC Entertainment',
  },
]);
const listMovie = ref([
  {
    image: 'movie-mutant.png',
    rating: '7.0',
    category: 'Action',
    title: 'The New Mutants',
    year: '2020',
  },
  {
    image: 'movie-soul.png',
    rating: '8.3',
    category: 'Action',
    title: 'Soul',
    year: '2020',
  },
  {
    image: 'movie-tenet.png',
    rating: '7.3',
    category: 'Action',
    title: 'Tenet',
    year: '2020',
  },
  {
    image: 'movie-guard.png',
    rating: '7.0',
    category: 'Action',
    title: 'The Old Guard',
    year: '2020',
  },
  {
    image: 'movie-project.png',
    rating: '7.0',
    category: 'Action',
    title: 'Project Power',
    year: '2020',
  },
]);
</script>
