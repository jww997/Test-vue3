<template>
  <h1>一个人的信息：</h1>
  <h2 v-show="person.name">姓名： {{ person.name }}</h2>
  <h2>年龄： {{ person.age }}</h2>
  <h2>工作种类： {{ person.job.type }}</h2>
  <h2>工作薪水： {{ person.job.salary }}</h2>
  <h3>爱好：{{ person.hobby }}</h3>
  <h3>测试的数据：{{ person.job.a.b.c }}</h3>
  <h3 v-show="person.sex">性别：{{ person.sex }}</h3>
  <button @click="changeInfo">修改人的信息</button>
  <button @click="addSex">添加一个sex属性</button>
  <button @click="deleteName">删除一个name属性</button>
</template>

<script>
import { ref, reactive } from "vue";
export default {
  name: "App",
  setup() {
    // 数据
    // let name = ref("张三");
    // let age = ref(18);
    // let job = reactive({
    //   type: "前端",
    //   salary: "30k",
    //   a: {
    //     b: {
    //       c: 666,
    //     },
    //   },
    // });
    // let hobby = reactive(["抽烟", "喝酒", "烫头"]);
    let person = reactive({
      name: "张三",
      age: 18,
      job: {
        type: "前端",
        salary: "30k",
        a: {
          b: {
            c: 666,
          },
        },
      },
      hobby: ["抽烟", "喝酒", "烫头"],
    });

    // 方法
    function changeInfo() {
      // name = "李四";
      // age = 48;
      // name.value = "李四";
      // age.value = 48;
      // console.log(name, age);
      // console.log(job);
      // job.type = "后端";
      // job.salary = "40k";
      // job.a.b.c = 999;
      // hobby[0] = "学习";

      person.name = "李四";
      person.age = 48;
      person.job.type = "后端";
      person.job.salary = "40k";
      person.job.a.b.c = 999;
      person.hobby[0] = "学习";
    }

    function addSex() {
      person.sex = "男";
    }
    function deleteName() {
      delete person.name;
    }

    // 返回一个对象（常用）
    return {
      // name,
      // age,
      // job,
      // hobby,
      person,
      changeInfo,
      addSex,
      deleteName,
    };
  },
};
</script>

<style>
</style>
