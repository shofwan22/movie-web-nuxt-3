<template>
  <div>
    <div class="section-carousel h-[597px]"></div>
    <div class="section-base h-[333px] bg-white/[.05] px-20 pt-[89px]">
      <div class="flex items-center justify-between">
        <BaseTitleSection title="Discover Movies" />
        <BaseTabMenu menu-one="Popularity" menu-two="Release Date" />
      </div>
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
    <div class="section-discover h-[764px] px-20"></div>
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
]);
</script>
