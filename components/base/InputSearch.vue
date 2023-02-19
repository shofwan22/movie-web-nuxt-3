<template>
  <div class="ml-9 relative">
    <div
      class="relative w-[571px] h-9 bg-black/[.13] rounded flex items-center focus:bg-[#1A1E24]"
    >
      <img
        src="~/assets/images/ic_movie.svg"
        alt="ic movie"
        class="h-4 w-5 absolute left-2.5"
      />
      <input
        type="text"
        placeholder="Find Movie"
        v-model="searchValue"
        @input="search"
        class="pl-[47px] pr-9 text-base text-[#E5E5E5] bg-transparent focus:outline-none focus:bg-[#1A1E24] w-full h-full rounded"
      />
      <img
        src="~/assets/images/ic_search.svg"
        alt="ic search"
        class="h-4 w-4 absolute right-4"
      />
    </div>
    <div
      v-if="searchValue"
      class="bg-black/[.9] w-full absolute rounded-b-[8px] py-[18px] px-[19px] text-[#E5E5E5] text-[14px] font-semibold"
    >
      <ul v-if="searchResult.length > 0">
        <li v-for="(data, index) in searchResult" :key="index" class="mb-1">
          {{ data }}
        </li>
      </ul>
      <p v-else>No Result</p>
    </div>
  </div>
</template>

<script setup>
const searchValue = ref('');
const listMovies = [
  'Superman',
  'Wonder Woman 1984',
  'Wonder Woman',
  'Wonder Park',
];
const searchResult = ref([]);
const search = () => {
  if (searchValue.value) {
    const search = listMovies.filter((str) => {
      const data = str.toLowerCase();
      const searching = searchValue.value.toLowerCase();
      return data.indexOf(searching) !== -1;
    });
    searchResult.value = search;
  } else {
    searchResult.value = [];
  }
};
</script>
