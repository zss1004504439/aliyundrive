<template>
  <section class="file-folder">
    <FolderActions></FolderActions>
    <FileList></FileList>
  </section>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";
import FileList from "./FileList.vue";
import FolderActions from "./FolderActions.vue";
export default defineComponent({
  name: "FileFolder",
  components: {
    FolderActions,
    FileList,
  },
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