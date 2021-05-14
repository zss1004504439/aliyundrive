<template>
  <section class="file-list">file-list</section>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "FileList",
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