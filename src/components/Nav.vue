<template>
  <nav class="nav">
    <div
      v-for="item in navList"
      :key="item.id"
      class="nav-item"
      @click="onClick(item)"
    >
      <span class="nav-icon"></span>
      <span class="nav-title">{{ item.title }}</span>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";
import { INavItem } from "../Drive";

export default defineComponent({
  name: "Nav",
  emits: ["onClick"],
  setup(props, ctx) {
    const state = reactive({
      navList: <INavItem[]>[
        {
          id: 1,
          title: "Tab 1",
        },
        {
          id: 2,
          title: "Tab 2",
        },
      ],
    });
    const onClick = (item:INavItem) => {
      ctx.emit("onClick", item);
    };
    return {
      ...toRefs(state),
      onClick,
    };
  },
});
</script>

<style lang="less" scoped>
.nav {
  flex: 1;
}
.nav-item {
  display: flex;
  border-radius: 10px;
  position: relative;
  align-items: center;
  height: 44px;
  padding-left: 12px;
  // line-height: 14px;
  box-sizing: border-box;
  width: 216px;
  margin: 0 auto;
  cursor: pointer;
  font-size: 14px;
  .nav-icon {
    width: 24px;
    height: 24px;
    font-size: 24px;
    margin-right: 16px;
  }
  .nav-title {
  }
  &:hover {
    background-color: rgba(132, 133, 141, 0.08);
  }
}
</style>

 