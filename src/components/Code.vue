<template>
  <div class="codeblock">
    <p class="code" v-for="line in codes" :key="line.id">
      {{ line.id + "&nbsp;".repeat(line.space * 2 + 1) }}
      <span v-html="line.text"></span>
    </p>
  </div>
</template>


<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    codes: {
      type: Object,
      required: true,
    },
  },
  setup() {},
});
</script>
