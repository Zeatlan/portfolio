<template>
  <div id="skills">
    <carousel :items-to-show="2.95" :wrap-around="true">
      <slide v-for="(slide, i) in slides" :key="i">
        <div class="line" />
        <SkillsPoint :title="slide.title" :image="slide.image" />
      </slide>

      <template #addons="{ slidesCount }">
        <Navigation v-if="slidesCount > 3" />
      </template>
    </carousel>
  </div>
</template>


<script lang="ts">
import { defineComponent, ref } from "vue";
import type { Ref } from "vue";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";
import SkillsPoint from "./SkillsPoint.vue";

interface Slide {
  title: string;
  image: string;
}

export default defineComponent({
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
    SkillsPoint,
  },
  setup() {
    const slides: Ref<Array<Slide>> = ref<Array<Slide>>([
      {
        title: "Typescript",
        image:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1024px-Typescript_logo_2020.svg.png",
      },
      {
        title: "NodeJS",
        image:
          "https://assets.stickpng.com/images/62a7524a223343fbc2207d08.png",
      },
      {
        title: "VueJS",
        image:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/2367px-Vue.js_Logo_2.svg.png",
      },
      {
        title: "NuxtJS",
        image:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Nuxt_logo.svg/2560px-Nuxt_logo.svg.png",
      },
      {
        title: "Sass",
        image:
          "https://sass-lang.com/assets/img/styleguide/seal-color-aef0354c.png",
      },
      {
        title: "MySQL",
        image: "https://cdn-icons-png.flaticon.com/512/5968/5968313.png",
      },
      {
        title: "Firebase",
        image:
          "https://assets.stickpng.com/images/5847f40ecef1014c0b5e488a.png",
      },
    ]);

    return { slides };
  },
});
</script>
