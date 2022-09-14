<template>
  <button :class="cls"><slot /></button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    cls: {
      type: String,
      required: false,
      default: "action",
    },
  },
  setup() {},
});
</script>
