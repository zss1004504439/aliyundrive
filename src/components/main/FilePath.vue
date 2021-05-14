<template>
  <section class="file-path">FilePath</section>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "FilePath",
  setup() {
    const state = reactive({
      fileList: [],
    });

    return {
      ...toRefs(state),
    };
  },
});
</script>

<style scoped>
</style>