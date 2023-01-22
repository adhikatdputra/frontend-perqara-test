<template>
  <div class="home">
    <Header />
    <div class="relative pt-14 pb-12">
      <div class="bg-[#292e36] absolute top-0 left-0 h-[350px] w-full"></div>
      <div class="container mx-auto py-16 px-5 sm:px-8">
        <div class="h-2 w-32 bg-red-600 mb-3 relative"></div>
        <div class="block items-center justify-between mb-12 relative sm:flex">
          <div class="font-semibold text-white text-4xl pb-4 sm:pb-0">
            Movies
          </div>
        </div>
        <div class="relative block sm:flex">
          <div class="w-full mr-5 mb-5 sm:w-[240px]">
            <div class="rounded-lg text-white bg-[#0f1824] py-6">
              <div
                class="font-bold text-white text-base px-5 pb-5 border-b border-solid border-[#262f38]"
              >
                Sort Result By
              </div>
              <div
                class="font-bold text-white text-base px-5 py-3 mb-5 border-b border-t border-solid border-[#262f38]"
              >
                Genres
              </div>
              <div
                class="flex items-center justify-between px-5 py-1"
                v-for="(i, idx) in cate"
                :key="idx"
              >
                <span>{{ i }}</span>
                <input
                  type="checkbox"
                  :id="i"
                  :value="i"
                  v-model="checkedNames"
                />
              </div>
            </div>
          </div>
          <div class="w-full sm:w-[calc(100%-250px)]">
            <div class="flex flex-wrap -mx-2">
              <div
                class="w-1/2 px-3 sm:w-1/4"
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
                    <div class="text-white opacity-25 text-sm">
                      {{ film.year }}
                    </div>
                  </div>
                </div>
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
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import dataFilm from "./../../film.json";
import { ref } from "vue";

export default {
  name: "HomeView",
  components: {
    Footer,
    Header,
  },
  data() {
    return {
      data: dataFilm.film,
      checkedNames: ref([]),
      cate: [
        "Action",
        "Adventure",
        "Animation",
        "Comedy",
        "Crime",
        "Documentary",
        "Drama",
        "Family",
        "Fantasy",
        "History",
        "Horror",
      ],
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
