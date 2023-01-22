<template>
  <div class="home">
    <Header />
    <div class="v pt-36 pb-12">
      <carousel
        :autoplay="true"
        :nav="false"
        :dots="true"
        :loop="true"
        :items="1"
        :margin="30"
        :center="true"
        :stagePadding="420"
        :responsive="{
          0: { items: 1, stagePadding: 50 },
          600: { items: 1, stagePadding: 420 },
        }"
      >
        <div class="flex-card items-center" v-for="i in 4" :key="i">
          <div class="thumb">
            <img src="@/assets/img/film/wonder-women.png" alt="" />
          </div>
          <div class="bg-black p-6 pb-6 sm:pb-16 text-white data">
            <div class="flex">
              <img
                src="@/assets/img/icn-star.svg"
                alt=""
                class="w-5 leading-0 star"
              />
              <span class="text-white font-semibold text-lg pl-2 pt-1"
                >7.3</span
              >
            </div>
            <div class="text-2xl font-medium">Space Sweepers</div>
            <div class="text-base py-3">
              2021 <span class="text-3xl text-grey">•</span> Sci-Fi
            </div>
            <div class="text-xs hidden sm:block">
              When the crew of a space junk collector ship called The Victory
              discovers a humanoid robot named Dorothy that's known to be a
              weapon of mass destruction, they get involved in a risky business
              deal which puts their lives at stake.
            </div>
          </div>
        </div>
      </carousel>
    </div>
    <div class="relative">
      <div class="bg-[#292e36] absolute top-0 left-0 h-[300px] w-full"></div>
      <div class="container mx-auto py-16 px-5 sm:px-8">
        <div class="h-2 w-32 bg-red-600 mb-3 relative"></div>
        <div class="block items-center justify-between mb-12 relative sm:flex">
          <div class="font-semibold text-white text-2xl pb-4 sm:pb-0">
            Discover Movies
          </div>
          <div>
            <button
              class="rounded-full bg-red-600 py-1 px-5 text-white text-sm font-semibold"
            >
              Popularity
            </button>
            <button
              class="rounded-full bg-black py-1 px-5 text-white text-sm font-semibold bg-opacity-25 ml-4"
            >
              Release Date
            </button>
          </div>
        </div>
        <div class="flex flex-wrap -mx-2">
          <div
            class="w-1/2 px-3 sm:w-1/5"
            v-for="(film, idx) in data"
            :key="idx"
          >
            <div class="mb-5">
              <div class="relative group overflow-hidden">
                <img
                  :src="require(`@/assets/img/film/${film.thumbnail}`)"
                  alt=""
                  class="w-full"
                />
                <div
                  class="absolute top-0 right-0 text-white font-bold pr-1 pl-1 bg-black bg-opacity-50"
                >
                  {{ float(film.rating) }}
                </div>
                <div
                  class="absolute bg-gray-900 w-full top-[1000px] ease-in-out duration-300 h-full flex items-center justify-center group-hover:top-0"
                >
                  <div class="text-center">
                    <div class="flex justify-center">
                      <img
                        src="@/assets/img/icn-star.svg"
                        alt=""
                        class="w-5 leading-0"
                      />
                      <span
                        class="text-white font-semibold text-lg pl-2 pt-1"
                        >{{ float(film.rating) }}</span
                      >
                    </div>
                    <div class="my-12 text-white font-semibold text-lg">
                      Action
                    </div>
                    <router-link to="/movie/detail">
                      <button
                        class="rounded-full bg-red-600 py-1 px-5 text-white text-sm font-semibold"
                      >
                        VIEW
                      </button>
                    </router-link>
                  </div>
                </div>
              </div>
              <div>
                <div class="text-white font-semibold pt-2 text-base">
                  {{ film.name }}
                </div>
                <div class="text-white opacity-25 text-sm">{{ film.year }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import carousel from "vue-owl-carousel";
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import dataFilm from "./../../film.json";
export default {
  name: "HomeView",
  components: {
    Footer,
    Header,
    carousel,
  },
  data() {
    return {
      data: dataFilm.film.slice(0, 10),
    };
  },
  methods: {
    float(i) {
      return i.toFixed(1);
    },
  },
  mounted() {
    // console.log(this.data);
  },
};
</script>
<style lang="scss" scoped>
.owl-carousel {
  .owl-item {
    .flex-card {
      opacity: 0.5;
      display: block;

      .thumb {
        line-height: 0;
        width: 100%;

        img {
          width: 100%;
        }
      }

      .data {
        width: calc(100% - 0%);
        .star {
          width: 1.25rem !important;
        }
      }
    }
  }
}

@media (min-width: 414px) {
  .owl-carousel {
    .owl-item {
      .flex-card {
        opacity: 0.5;
        display: flex;

        .thumb {
          line-height: 0;
          width: 40%;

          img {
            width: 100%;
          }
        }

        .data {
          width: calc(100% - 40%);
          .star {
            width: 1.25rem !important;
          }
        }
      }
    }
  }
}

.owl-carousel {
  .owl-item.center {
    .flex-card {
      opacity: 1 !important;
    }
  }
}
</style>

<style>
.autocomplete-result-list {
  background: #1e2329 !important;
}
.owl-theme .owl-dots .owl-dot.active span {
  background: #e74c3c;
  width: 50px;
}

.owl-theme .owl-dots .owl-dot:hover span {
  background: #e74c3c;
}

.owl-theme .owl-dots .owl-dot span {
  width: 10px;
  height: 10px;
  margin: 5px 7px;
  background: rgba(255, 255, 255, 0.5);
  display: block;
  -webkit-backface-visibility: visible;
  transition: opacity 200ms ease;
  border-radius: 30px;
}

.owl-theme .owl-nav.disabled + .owl-dots {
  margin-top: 50px;
}
</style>
