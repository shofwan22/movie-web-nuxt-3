<template>
  <div class="pt-[122px] slider-movie">
    <div v-for="(movie, index) in listMovies" :key="index">
      <BaseCardCarousel
        :image="movie.image"
        :rating="movie.rating"
        :title="movie.title"
        :year="movie.year"
        :category="movie.category"
        :description="movie.description"
      />
    </div>
  </div>
</template>

<script setup>
const listMovies = ref([
  {
    image: 'movie-space.png',
    rating: '7.3',
    title: 'Space Sweepers',
    year: '2021',
    category: 'Sci-Fi',
    description:
      "When the crew of a space junk collector ship called The Victory discovers a humanoid robot named Dorothy that's known to be a weapon of mass destruction, they get involved in a risky business deal which puts their lives at stake.",
  },
  {
    image: 'movie-boys.png',
    rating: '8.1',
    title: 'To All the Boys: Always and Forever',
    year: '2021',
    category: 'Drama',
    description:
      'Senior year of high school takes center stage as Lara Jean returns from a family trip to Korea and considers her college plans — with and without Peter.',
  },
  {
    image: 'movie-news.png',
    rating: '7.2',
    title: 'News of the World',
    year: '2021',
    category: 'Drama',
    description:
      'A Texan traveling across the wild West bringing the news of the world to local townspeople, agrees to help rescue a young girl who was kidnapped.',
  },
]);
const sliderOptions = ref({
  centerMode: true,
  centerPadding: '435px',
  slidesToShow: 1,
  speed: 300,
  index: 1,
  arrows: true,
  autoplay: false,
  autoplaySpeed: 500,
  pauseOnHover: false,
  pauseOnFocus: false,
  dots: true,
  dotsClass: 'custom-dots',
  customPaging: function (slider, i) {
    let slideNumber = i + 1,
      totalSlides = slider.slideCount;
    return (
      '<a class="dot" role="button" title="' +
      slideNumber +
      ' of ' +
      totalSlides +
      '"><span class="string">' +
      slideNumber +
      '/' +
      totalSlides +
      '</span></a>'
    );
  },
  responsive: [
    {
      breakpoint: 480,
      settings: {
        arrows: false,
        centerMode: true,
        centerPadding: '15px',
        slidesToShow: 1,
      },
    },
  ],
});

const chooseImage = (image) => {
  const allImages = import.meta.glob('~/assets/images/*.png');
  return allImages[`/assets/images/${image}`]().then((mod) => {
    return mod.default;
  });
};

const initSlider = () => {
  $('.slider-movie').slick(sliderOptions.value);
};

const load = ref(false);

onMounted(() => {
  listMovies.value.map((list, index) => {
    chooseImage(list.image).then((result) => {
      list.image = result;
      if (list.image === result && index + 1 == listMovies.value.length) {
        initSlider();
        const prevSlickCloned = document.querySelectorAll(
          '[data-slick-index="-1"]'
        );
        prevSlickCloned[0].children[0].children[0].children[0].src = list.image;
      }
    });
  });
});
</script>

<style lang="postcss">
.slick-slide {
  opacity: 0.5;
}
.slick-slide.slick-current.slick-active {
  opacity: 1;
}
.custom-dots {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-left: 0;
  padding-top: 51px;
}

.custom-dots li {
  margin: 0 0 0 18px;
  display: inline-block;
  list-style: none;
}
.custom-dots li:first-child {
  margin-left: 0;
}
.custom-dots .dot {
  display: block;
  width: 12px;
  height: 12px;
  text-decoration: none;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 6px;
  cursor: pointer;
}
.custom-dots .dot .string {
  position: absolute;
  left: -99999px;
  line-height: 0;
  opacity: 0;
}
.custom-dots .slick-active .dot {
  width: 60px;
  height: 12px;
  background: #e74c3c;
  border-radius: 6px;
}
.custom-dots .dot:hover,
.custom-dots .slick-active .dot:hover {
  background-color: #e74c3c;
}
</style>
