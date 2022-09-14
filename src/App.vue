
<template>
  <page-loader @loading-finished="isLoading = false" />

  <Header v-if="!isLoading" />

  <RouterView v-if="!isLoading" />
</template>

<script lang="ts">
import { RouterLink, RouterView } from "vue-router";
import { defineComponent, ref } from "vue";
import type { Ref } from "vue";
import Header from "./components/Header.vue";
import PageLoader from "./components/PageLoader.vue";

export default defineComponent({
  name: "App",
  components: { Header, PageLoader },
  setup() {
    const isLoading: Ref<Boolean> = ref(true);
    return { isLoading };
  },
});
</script>