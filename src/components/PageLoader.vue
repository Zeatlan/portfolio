<template>
  <div class="page-loader" v-if="!isLoaded">
    <div class="losange">
      <div class="line bottom"></div>
      <div class="line left"></div>
      <div class="line top"></div>
      <div class="line right"></div>
      <h1>A</h1>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, ref } from "vue";
import type { Ref } from "vue";
import { gsap } from "gsap";

export default defineComponent({
  name: "PageLoader",
  setup(props, { emit }) {
    const isLoaded: Ref<boolean> = ref(false);

    const leftTl = gsap.timeline();
    const rightTl = gsap.timeline();

    onMounted(() => {
      setTimeout(() => {
        gsap.to("h1", { backgroundPosition: "0 100%", duration: 0.6 });

        leftTl
          .to(".bottom", { "--loader-border": "white", duration: 0.5 })
          .to(".left", { "--loader-border": "white", duration: 0.5 });

        rightTl
          .to(".right", { "--loader-border": "white", duration: 0.5 })
          .to(".top", { "--loader-border": "white", duration: 0.5 })
          .then(() => {
            if (!leftTl.isActive() && !rightTl.isActive()) {
              gsap
                .to(".losange", { scale: 0.3, x: -150, y: -370, duration: 0.5 })
                .then(() => {
                  isLoaded.value = true;
                  emit("loadingFinished", true);
                });
            }
          });
      }, 1300);
    });

    return { isLoaded };
  },
});
</script>