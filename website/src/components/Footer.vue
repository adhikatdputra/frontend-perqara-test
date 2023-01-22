<template>
  <div class="bg-[#16191E]">
    <div class="container mx-auto lg:px-8 py-9">
      <div class="block items-center justify-between text-center sm:flex">
        <img
          src="@/assets/img/logo-grey.png"
          alt=""
          class="h-8 mx-auto block sm:hidden mb-4"
        />
        <div class="text-grey text-xs">
          © 2023 MoovieTime. All rights reserved.
        </div>
        <img
          src="@/assets/img/logo-grey.png"
          alt=""
          class="h-8 mx-auto hidden sm:block"
        />
        <div class="text-grey text-xs">Made with VUEJS</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterComp",
};
</script>
