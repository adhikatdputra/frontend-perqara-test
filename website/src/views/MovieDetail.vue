<template>
  <div class="home">
    <Header />
    <div class="relative pt-14">
      <div class="banner relative">
        <img
          src="@/assets/img/banner.png"
          alt=""
          class="h-[400px] object-cover w-full object-top"
        />
        <div
          class="absolute h-[80px] w-full left-0 bottom-0 bg-black opacity-50"
        ></div>
        <div class="absolute -bottom-[40%] mb-8 w-full z-10">
          <div class="container mx-auto px-5 sm:px-8">
            <div class="text-center block text-white pb-4 sm:hidden">
              <div class="text-lg">2020</div>
              <div class="font-semibold text-3xl">Wonder Woman 1984</div>
              <div class="text-sm">Fantasy, Action, Adventure</div>
            </div>
            <div class="flex items-center">
              <img
                src="@/assets/img/film/wonder-women.png"
                alt=""
                class="w-[60%] mx-auto sm:w-[220px]"
              />
              <div class="ml-7 text-white hidden sm:block">
                <div class="text-lg">2020</div>
                <div class="font-semibold text-3xl">Wonder Woman 1984</div>
                <div class="text-sm">Fantasy, Action, Adventure</div>

                <div class="flex items-center pt-8 pb-14">
                  <div class="flex items-center">
                    <img src="@/assets/img/icn-star.svg" alt="" />
                    <span class="font-semibold text-3xl ml-3 pt-1">7.0</span>
                  </div>
                  <div class="px-5 border-r border-solid border-[#4E4D4D]">
                    <div class="text-sm uppercase opacity-50">User Score</div>
                    <div class="text-sm uppercase -mt-1">3621 Votes</div>
                  </div>
                  <div class="px-5 border-r border-solid border-[#4E4D4D]">
                    <div class="text-sm uppercase opacity-50">Status</div>
                    <div class="text-sm uppercase -mt-1">Released</div>
                  </div>
                  <div class="px-5 border-r border-solid border-[#4E4D4D]">
                    <div class="text-sm uppercase opacity-50">language</div>
                    <div class="text-sm uppercase -mt-1">english</div>
                  </div>
                  <div class="px-5 border-r border-solid border-[#4E4D4D]">
                    <div class="text-sm uppercase opacity-50">budget</div>
                    <div class="text-sm uppercase -mt-1">$200,000,000.00</div>
                  </div>
                  <div class="px-5">
                    <div class="text-sm uppercase opacity-50">production</div>
                    <div class="text-sm uppercase -mt-1">DC Entertainment</div>
                  </div>
                </div>
                <div>
                  <div class="text-sm mb-3 font-semibold text-red-600">
                    OVERVIEW
                  </div>
                  <div class="text-sm w-[55%] text-black">
                    Wonder Woman comes into conflict with the Soviet Union
                    during the Cold War in the 1980s and finds a formidable foe
                    by the name of the Cheetah.
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- <div class="container mx-auto py-16 px-5 sm:px-8"></div> -->
      <div class="bg-white">
        <div class="container mx-auto py-16 pt-40 px-5 sm:px-8">
          <carousel
            :autoplay="true"
            :nav="false"
            :dots="false"
            :loop="true"
            :items="1"
            :margin="10"
            :responsive="{
              0: { items: 1 },
              600: { items: 2 },
            }"
          >
            <div class="p-2" v-for="i in 4" :key="i">
              <div class="testi">
                <div class="flex items-center justify-between">
                  <div class="flex items-center">
                    <div class="profile">
                      <img
                        src="https://source.unsplash.com/random/100x100"
                        alt=""
                      />
                    </div>
                    <div class="ml-2">
                      <div class="text-sm">SWITCH.</div>
                      <div class="text-xs text-[#666666]">
                        December 18, 2020
                      </div>
                    </div>
                  </div>
                  <div class="flex items-start rating">
                    <div class="rate">
                      <img src="@/assets/img/icn-star.svg" alt="" />
                    </div>
                    <span class="font-bold text-3xl pl-1">7.0</span>
                  </div>
                </div>
                <div class="pt-5 italic text-xs">
                  It isn't as easy as saying 'Wonder Woman 1984' is a good or
                  bad movie. The pieces are there, and there are moments I
                  adore, but it does come across as a bit of a mess, even though
                  the action sequences are breathtaking. If you're a fan of the
                  original film, you'll be more willing to take the ride, but
                  for those more indifferent, it may be a bit of a blander sit.
                  If you can and are planning to watch it, the theatrical
                  experience is the way to go - there is nothing like seeing
                  these stunning sets, fun action scenes and hearing Zimmer's
                  jaw-dropping score like on the big screen. - Chris dos Santos.
                </div>
              </div>
            </div>
          </carousel>
        </div>
      </div>
      <!-- Recomendasi -->
      <div class="container mx-auto py-16 px-5 sm:px-8">
        <div class="text-white text-lg mb-8">RECOMMENDATION MOVIES</div>
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
import { ref } from "vue";

export default {
  name: "HomeView",
  components: {
    Footer,
    Header,
    carousel,
  },
  data() {
    return {
      data: dataFilm.film.slice(0, 5),
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
.testi {
  background: #f9f9f9;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.1);
  border-radius: 14px;
  padding: 25px;

  .profile {
    line-height: 0;
    width: 48px;

    img {
      width: 48px !important;
      height: 48px;
      object-fit: cover;
      border-radius: 50%;
    }
  }

  .rating {
    background: rgba(196, 196, 196, 0.28);
    border-radius: 7px;
    padding: 5px;
    img {
      width: 17px !important;
    }
  }
}
</style>
