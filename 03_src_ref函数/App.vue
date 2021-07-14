<template>
  <h1>一个人的信息：</h1>
  <h2>姓名： {{ name }}</h2>
  <h2>年龄： {{ age }}</h2>
  <h2>工作种类： {{ job.type }}</h2>
  <h2>工作薪水： {{ job.salary }}</h2>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  setup() {
    // 数据
    let name = ref("张三");
    let age = ref(18);
    let job = ref({
      type: "前端",
      salary: "30k",
    });

    // 方法
    function changeInfo() {
      // name = "李四";
      // age = 48;
      name.value = "李四";
      age.value = 48;
      console.log(name, age);
      console.log(job);
      job.value.type = "后端";
      job.value.salary = "40k";
    }

    // 返回一个对象（常用）
    return {
      name,
      age,
      job,
      changeInfo,
    };
  },
};
</script>

<style>
</style>
