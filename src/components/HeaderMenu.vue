<template>
  <div class="mobile-menu" :class="burger ? 'active' : ''">
    <span class="close" @click="$emit('burgerMenu')">
      <svg width="28" viewBox="0 0 25 25" class="fill-current">
        <path
          d="M22.222 0 25 2.778l-9.723 9.721L25 22.222 22.222 25 12.5 15.277 2.778 25 0 22.222 9.722 12.5 0 2.778 2.778 0 12.5 9.722 22.222 0z"
          class="fill-current"
          fill-rule="evenodd"
        ></path>
      </svg>
    </span>

    <HeaderMenuList />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HeaderMenuList from "./HeaderMenuList.vue";
import Blob from "./svg/Blob.vue";

export default defineComponent({
  name: "HeaderMenu",
  components: { HeaderMenuList, Blob },
  props: {
    burger: {
      type: Boolean,
      required: true,
    },
  },
  setup() {},
});
</script>