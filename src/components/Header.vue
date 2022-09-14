<template>
  <header>
    <div class="wrapper">
      <nav>
        <div id="logo">
          <div class="losange-head">
            <h1>A</h1>
          </div>
        </div>

        <div class="lighting"></div>

        <div class="burger" @click="burgerMenu">
          <span class="line line1"></span>
          <span class="line line2"></span>
          <span class="line line3"></span>
        </div>

        <HeaderMenu :burger="burger" @burger-menu="burgerMenu" />
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import type { Ref } from "vue";
import HeaderMenu from "./HeaderMenu.vue";
import { gsap } from "gsap";

export default defineComponent({
  name: "App",
  setup() {
    const burger: Ref<boolean> = ref(false);
    const burgerMenu = () => {
      burger.value = !burger.value;
    };

    return { burger, burgerMenu };
  },
  components: { HeaderMenu },
});
</script>