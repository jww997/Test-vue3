<template>
  <h2>我是Test组件</h2>
  <h2>当前点击时鼠标的坐标为：x:{{ point.x }} y:{{ point.y }}</h2>
</template>

<script>
// import { ref } from "@vue/reactivity";
import usePoint from "../hooks/usePoint";
export default {
  name: "Test",
  setup() {
    // let name = ref("tom");
    const point = usePoint();
    // return { name, point };
    return { point };
  },
};
</script>
