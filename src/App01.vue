<script>
export default {
  data() {
    return {
      num: 0,
      age: 22,
      msg: "<h2>标题</h2>",
      id: "d1",
      url: "https://img11.360buyimg.com/n5/jfs/t1/215591/9/15397/277315/62399fadEd3a18078/ad6ce4c5d2a5d1dc.jpg",
      attributeName: 'id'
    };
  },
  methods: {
    changeName: function () {
      this.num = 12;
    },
  }
}
</script>

<template>
  <div>
    <p>{{ num }}</p>
    <p>{{ age }}</p>
    <button @click="changeName">changeName</button>

    <!--    v-once:当数据改变时,插值处的内容不会更新-->
    <!--    输出还是0-->
    <p v-once>{{ num }}</p>
    <!--    v-html:拼接html-->
    <p v-html="msg"></p>
    <!--    v-bind:动态绑定属性的内容-->
    <p v-bind:id="id">v-bind:id</p>
    <img v-bind:src="url"/>
    <!--    v-bind语法糖-->
    <p :id="id">:id</p>
    <!-- 使用javascript表达式   -->
    <p>{{ num + 2 }}</p>


    <!--    动态参数-->
    <!--动态属性-->
    <p v-bind:[attributeName]="id">v-bind:动态属性</p>
    <button @click="attributeName='class'">改变属性</button>
  </div>
</template>

<style>
#d1 {
  color: red;
}

.d1 {
  color: blue;
  font-size: 20px;
}
</style>