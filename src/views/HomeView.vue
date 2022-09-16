<template>
  <main>
    <Hero />
    <Skills />
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Hero from "../components/Hero.vue";
import Skills from "../components/Skills.vue";

export default defineComponent({
  components: {
    Hero,
    Skills,
  },
});
</script>
