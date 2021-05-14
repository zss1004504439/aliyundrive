<template>
  <section class="file-actions">FileActions</section>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "FileActions",
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