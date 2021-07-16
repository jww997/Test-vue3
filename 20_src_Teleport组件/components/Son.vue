<template>
  <div class="son">我是Son组件</div>
  <Dialog />
</template>

<script>
import Dialog from "./Dialog.vue";
export default {
  name: "Son",
  components: { Dialog },
};
</script>

<style>
.son {
  background-color: orange;
  padding: 10px;
}
</style>