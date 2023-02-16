<template>
  <div>
    <div class="section-hero h-[389px] bg-white/[.05] pt-[119px] px-20">
      <BaseTitleSection title="Movies" text-size="text-[36px]" />
      <div class="mt-[59] flex justify-between">
        <div
          class="w-[240px] h-[586px]"
          style="
            background: linear-gradient(
              180deg,
              #0e1723 0%,
              rgba(30, 35, 42, 0) 100%
            );
          "
        >
          sort
        </div>
        <div>
          <div class="grid grid-cols-4 gap-x-5 gap-y-9">
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
          <div class="flex justify-center mt-[63px]">
            <div
              class="rounded-[32px] bg-[#FF0000] text-[#E5E5E5] text-base font-semibold pt-[6px] pb-[9px] w-[151px] text-center cursor-pointer"
            >
              Load More
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="section-content h-[1255px]"></div>
  </div>
</template>

<script setup>
const listMovie = ref([
  {
    image: 'movie-wonder.png',
    rating: '7.0',
    category: 'Action',
    title: 'Wonder Woman 1984',
    year: '2020',
  },
  {
    image: 'movie-below.png',
    rating: '6.4',
    category: 'Action',
    title: 'Below Zero',
    year: '2021',
  },
  {
    image: 'movie-little.png',
    rating: '6.3',
    category: 'Action',
    title: 'The Little Things',
    year: '2021',
  },
  {
    image: 'movie-outside.png',
    rating: '6.5',
    category: 'Action',
    title: 'Outside the Wire',
    year: '2021',
  },
  {
    image: 'movie-black.png',
    rating: '5.1',
    category: 'Action',
    title: 'Black Water: Abyss',
    year: '2021',
  },
  {
    image: 'movie-breach.png',
    rating: '4.6',
    category: 'Action',
    title: 'Breach',
    year: '2021',
  },
  {
    image: 'movie-soul.png',
    rating: '8.3',
    category: 'Action',
    title: 'Soul',
    year: '2020',
  },
  {
    image: 'movie-fast.png',
    rating: '6.9',
    category: 'Action',
    title: 'Fast & Furious Present..',
    year: '2019',
  },
  {
    image: 'movie-croods.png',
    rating: '7.6',
    category: 'Action',
    title: 'The Croods: A New Age',
    year: '2020',
  },
  {
    image: 'movie-vanguard.png',
    rating: '6.3',
    category: 'Action',
    title: 'Vanguard',
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
    image: 'movie-wolf.png',
    rating: '5.9',
    category: 'Action',
    title: '100% Wolf',
    year: '2020',
  },
]);
</script>
