<template>
  <main>
    <Hero />
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Hero from "../components/Hero.vue";

export default defineComponent({
  components: {
    Hero,
  },
});
</script>
