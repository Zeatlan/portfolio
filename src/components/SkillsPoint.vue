<template>
  <div class="skill_point carousel__item">
    <div class="skill_content">
      <img :src="image" width="36" :alt="title" />
      <p>{{ title }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import type { Ref } from "vue";

export default defineComponent({
  props: {
    title: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
  },
});
</script>

<style>
</style>