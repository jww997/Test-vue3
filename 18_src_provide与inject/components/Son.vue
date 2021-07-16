<template>
  <div class="son">我是Son组件（孙）. {{ car.name }}-{{ car.price }}</div>
</template>

<script>
import { inject, toRefs } from "vue";
export default {
  name: "Son",
  setup() {
    let car = inject("car");
    return {
      car,
      // ...toRefs(car),
    };
  },
};
</script>

<style>
.son {
  background-color: orange;
  padding: 10px;
}
</style>