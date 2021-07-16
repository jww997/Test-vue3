<template>
  <div class="app">
    <h3>我是App组件（祖）</h3>
    <Child />
  </div>
</template>

<script>
import {
  ref,
  reactive,
  readonly,
  toRefs,
  isRef,
  isReactive,
  isProxy,
  isReadonly,
} from "vue";
export default {
  name: "App",
  setup() {
    let car = reactive({ name: "奔驰", price: "40W" });
    let sum = ref(0);
    let car2 = readonly(car);

    // sum = 2;

    console.log(isRef(sum));
    console.log(isReactive(car));
    console.log(isReadonly(car2));
    console.log(isProxy(car));
    console.log(isProxy(car2));
    console.log(isProxy(sum));

    return { ...toRefs(car) };
  },
};
</script> 

<style>
.app {
  background-color: gray;
  padding: 10px;
}
</style>