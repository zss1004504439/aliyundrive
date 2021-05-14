<template>
  <section class="folder-actions">FolderActions</section>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "FolderActions",
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