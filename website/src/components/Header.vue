<template>
  <div>
    <div class="bg-[#292e36] fixed w-full z-30 hidden sm:block">
      <div class="container mx-auto lg:px-8 py-4">
        <div class="flex items-center justify-between">
          <router-link to="/"
            ><img src="@/assets/img/logo.png" alt="" class="h-8"
          /></router-link>
          <div class="relative">
            <autocomplete
              :search="search"
              placeholder="Find movie"
              class="w-[550px] search text-white"
            ></autocomplete>
            <img
              src="@/assets/img/icn-film.svg"
              alt=""
              class="absolute top-1/2 -translate-y-1/2 ml-4"
            />
          </div>
          <div class="uppercase flex">
            <a
              href="#"
              class="text-white px-5 py-4 font-semibold flex relative group"
              ><img src="@/assets/img/icn-cate.svg" alt="" />
              <span class="pl-2">Categories</span>
              <div
                class="absolute top-12 rounded-md bg-white text-black p-4 z-10 hidden group-hover:block"
              >
                <a href="#"><div class="py-2">Action</div> </a>
                <a href="#"><div class="py-2">Adventure</div> </a>
                <a href="#"><div class="py-2">Animation</div> </a>
                <a href="#"><div class="py-2">Comedy</div> </a>
                <a href="#"><div class="py-2">Crime</div> </a>
                <a href="#"><div class="py-2">Documentary</div> </a>
                <a href="#"><div class="py-2">Drama</div> </a>
                <a href="#"><div class="py-2">Family</div> </a>
                <a href="#"><div class="py-2">Fantasy</div> </a>
                <a href="#"><div class="py-2">History</div> </a>
                <a href="#"><div class="py-2">Horror</div> </a>
              </div>
            </a>
            <router-link to="/movie" class="text-white px-5 py-4 font-semibold"
              >Movies</router-link
            >
            <a href="#" class="text-white px-5 py-4 font-semibold">TV Shows</a>
            <a href="#" class="text-white px-5 py-4 font-semibold">Login</a>
          </div>
        </div>
      </div>
    </div>
    <div class="bg-[#292e36] fixed w-full z-30 block px-5 sm:hidden">
      <div class="container mx-auto lg:px-8 py-4">
        <div class="flex items-center justify-between">
          <img src="@/assets/img/logo.png" alt="" class="h-8" />
          <a @click="open = !open">
            <img
              :src="
                require(`@/assets/img/${open ? 'icn-close' : 'icn-menu'}.png`)
              "
              alt=""
              class="h-8"
          /></a>
          <div
            class="fixed w-full h-[calc(100%+62px)] top-[62px] left-0 p-7 bg-[#292e36] overflow-scroll"
            v-if="open"
          >
            <div class="relative mb-12">
              <autocomplete
                :search="search"
                placeholder="Find movie"
                class="w-full search text-white"
              ></autocomplete>
              <img
                src="@/assets/img/icn-film.svg"
                alt=""
                class="absolute top-1/2 -translate-y-1/2 ml-4"
              />
            </div>
            <div class="uppercase">
              <a
                href="#"
                class="text-white px-5 py-4 font-semibold relative group"
                ><img
                  src="@/assets/img/icn-cate.svg"
                  alt=""
                  class="inline-block"
                />
                <span class="pl-3 pt-1">Categories</span>
                <div class="pt-4 px-7 z-10 hidden group-hover:block">
                  <a href="#"><div class="py-3">Action</div> </a>
                  <a href="#"><div class="py-3">Adventure</div> </a>
                  <a href="#"><div class="py-3">Animation</div> </a>
                  <a href="#"><div class="py-3">Comedy</div> </a>
                  <a href="#"><div class="py-3">Crime</div> </a>
                  <a href="#"><div class="py-3">Documentary</div> </a>
                  <a href="#"><div class="py-3">Drama</div> </a>
                  <a href="#"><div class="py-3">Family</div> </a>
                  <a href="#"><div class="py-3">Fantasy</div> </a>
                  <a href="#"><div class="py-3">History</div> </a>
                  <a href="#"><div class="py-3 pb-0">Horror</div> </a>
                </div>
              </a>
              <router-link
                to="/movie"
                class="block text-white px-5 py-4 pt-8 font-semibold"
                >Movies</router-link
              >
              <a href="#" class="block text-white px-5 py-4 font-semibold"
                >TV Shows</a
              >
              <a href="#" class="block text-white px-5 py-4 font-semibold"
                >Login</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderComp",
  data() {
    return {
      open: false,
      value: "",
      film: [
        "Wonder Woman 1984",
        "Below Zero",
        "The Little Things",
        "Outside the Wire",
        "Black Water: Abyss",
        "Breach",
        "Soul",
        "Fast & Furious Present",
        "The Croods: A New Age",
        "Vanguard",
      ],
    };
  },
  methods: {
    search(input) {
      if (input.length < 1) {
        return [];
      }
      return this.film.filter((film) => {
        return film.toLowerCase().startsWith(input.toLowerCase());
      });
    },
  },
};
</script>

<style lang="scss">
.search {
  .autocomplete-input {
    background: #1e2329;
    border: none;
  }

  .autocomplete-input:focus,
  .autocomplete-input[aria-expanded="true"] {
    background: #1e2329;
    border: none;
    outline: none;
    // box-shadow: 0 2px 2px rgb(0 0 0 / 16%);
    color: #e5e5e5;
  }
}
</style>
