<template>
  <h2>当前求和为：{{ sum }}</h2>
  <button @click="sum++">点我+1</button>
</template>

<script>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from "vue";
export default {
  name: "Demo",
  setup() {
    // 数据
    let sum = ref(0);

    console.log("---setup---");
    // 通过组合式API的形式去使用生命周期钩子
    // 函数体
    onBeforeMount(() => {
      console.log("---onBeforeMount---");
    });
    // 函数体
    onMounted(() => {
      console.log("---onMounted---");
    });
    // 函数体
    onBeforeUpdate(() => {
      console.log("---onBeforeUpdate---");
    });
    // 函数体
    onUpdated(() => {
      console.log("---onUpdated---");
    });
    // 函数体
    onBeforeUnmount(() => {
      console.log("---onBeforeUnmount---");
    });
    // 函数体
    onUnmounted(() => {
      console.log("---onUnmounted---");
    });

    // 返回一个对象（常用）
    return { sum };
  },
  // 通过配置项的形式使用生命周期钩子
  // #region
  beforeCreate() {
    console.log("---beforeCreate---");
  },
  created() {
    console.log("---created---");
  },
  beforeMount() {
    console.log("---beforeMount---");
  },
  mounted() {
    console.log("---mounted---");
  },
  beforeUpdate() {
    console.log("---beforeUpdate---");
  },
  updated() {
    console.log("---updated---");
  },
  // beforeDestroy() {
  //   console.log("---beforeDestroy---");
  // },
  // destroyed() {
  //   console.log("---destroyed---");
  // },
  beforeUnmount() {
    console.log("---beforeUnmount---");
  },
  unmounted() {
    console.log("---unmounted---");
  },
  // #endregion
};
</script>
