<script>
export default {
  data() {
    return {
      message: 'hello word'
    };
  },
  //  计算属性,有缓存,只要依赖值不变则不会重新计算
  computed: {
    //第一种写法
    // reverseMsg: function () {
    //   return this.message.split("").reverse().join("");
    // }

    //第二种写法
    reverseMsg: {
      //更改data数据会重新计算和渲染
      set:function (newValue){
        this.message=newValue;
      },
      get:function (){
        return this.message.split("").reverse().join("");
      }
    }
  }
}
</script>

<template>
  <div>
    <p>{{ message }}</p>
    <!--    使用计算属性-->
    <p>{{ reverseMsg }}</p>
    <button @click="reverseMsg='你好'" >test set</button>
    <!--    使用js表达式-->
    <p>{{message.split("").reverse().join("")}}</p>
  </div>
</template>

<style>
</style>