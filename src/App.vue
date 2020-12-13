<template>
  <div id="app">
    <!-- {{messages.name}}
    <span v-bind:title="message">啦啦啦阿联</span>
    <div v-for="(itme,index) in arr" :key="index">{{itme}}</div>
    <div v-if="false">11111111</div>
    <div v-else-if="true">222222</div>
    <div v-else>3333333</div>
    <div v-on:click="test">点我</div>
    <input type="text" v-model.number="message">
    <select v-model="ope">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="text" v-model.number="sub">
    <div v-if="ope=='+'">计算结果{{message+sub}}</div>
    <div v-if="ope=='-'">计算结果{{message-sub}}</div>
    <div v-if="ope=='*'">计算结果{{message*sub}}</div>
    <div v-if="ope=='/'">计算结果{{message/sub}}</div> -->

  <div v-for="itme in array " :key="itme.index">
        <div v-bind:class="[{btn:index==1,btn2:index==2,btn3:index==3},btn4]">{{itme.id}}</div>
        <div>{{itme.title}}</div>
        <div>{{itme.number}}</div>
        </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data:()=> {//函数data这样写就变成了属性名
    return {
      message:0,
      arr:[1,2,3,4,5],
      ope:"+",
      sub:0,
      messages:{
        name:"我是messages对象的属性"
      }
    }
  },
  methods: {
    test(){
      console.log("我是点击对象")
      
    }
  },
  array:[
        {
            id:1,
            title:"这个国家",
            number:"400万"
    },
     {
            id:2,
            title:"那个国家",
            number:"300万"
    },
     {
            id:3,
            title:"个国家",
            number:"200万"
    },
     {
            id:4,
            title:"国家",
            number:"100万"
    },
    ]
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
 .btn{
        color: rgb(241, 7, 7);
    }
    .btn2{
        color: rgb(218, 241, 7);
    }
    .btn3{
        color: rgb(241, 206, 7);
    }
    .btn4{
        color: rgb(10, 10, 10);
    }
</style>
