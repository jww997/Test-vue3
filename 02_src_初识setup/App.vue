<template>
  <h1>一个人的信息：</h1>
  <h2>姓名： {{ name }}</h2>
  <h2>年龄： {{ age }}</h2>
  <h2>性别： {{ sex }}</h2>
  <button @click="sayHello">说话(vue3所配置的--sayWelcome)</button>
  <br />
  <br />
  <button @click="sayWelcome">说话(vue2所配置的--sayWelcome)</button>
  <br />
  <br />
  <button @click="test1">测试一下vue2的配置中读取vue3的数据与方法</button>
  <br />
  <br />
  <button @click="test2">
    测试一下vue3中setup的配置中读取vue3的数据与方法
  </button>
</template>

<script>
// import {h} from 'vue'
export default {
  name: "App",
  data() {
    return { sex: "男", a: 100 };
  },
  methods: {
    sayWelcome() {
      alert("欢迎");
    },
    test1() {
      console.log(this.name);
      console.log(this.age);
      console.log(this.sex);
      console.log(this.sayHello);
    },
  },
  // 此处只是测试一下setup，暂时不考虑响应式
  setup() {
    // 数据
    let name = "张三";
    let age = 18;
    let a = 200;

    // 方法
    function sayHello() {
      alert(`我叫${name}, 我${age}, 你好啊！`);
    }
    function test2() {
      console.log(name);
      console.log(age);
      console.log(sayHello);
      console.log(this.sex);
      console.log(this.sayWelcome);
    }

    // 返回一个对象（常用）
    return {
      name,
      age,
      a,
      sayHello,
      test2,
    };

    // 返回一个函数（渲染函数）
    // return () => {return h('h1', '尚硅谷')}
  },
};
</script>

<style>
</style>
