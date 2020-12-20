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
  <!-- 新闻列表 -->
  <!-- <div v-bind:class="{ active : isActive }" v-for="(itme,index) in array" :key="index">
        <div v-bind:class="[{btn:index==0,btn2:index==1,btn3:index==2,btn4:index==3}]">{{itme.id}}</div>
        <div>{{itme.title}}</div>
        <div>{{itme.cont}}</div>
  </div> -->
   <!-- <div class="item" v-for="item in news" :key="item.index">
      <div
        v-bind:class="[item.index==1?'cls1':item.index==2?'cls2':item.index==3?'cls3':'cls']"
      >{{item.index}}</div>
      <div>{{item.title}}</div>
      <div>{{item.count}}万</div>
    </div>-->
    <!-- 随机数 -->
    <!-- <div v-for="sui in arr" :key="sui.index">
      {{arr[sji]=Math.floor(Math.random()*arr.length+1)}}
    </div> -->
    <!-- 随机点名 -->
      <!-- <div class="system" v-bind:title="message">
        {{message}}
      <div class="system-top">
        <input type="text" v-model="inp" >
        <button v-on:click="entering">录入</button>
      </div>
      <div class="dianming">
      <button v-on:click="kaish">开始随机点名</button>
      <button v-on:click="jiesh">结束随机点名</button>
      </div>
      <div v-bind:class="{xianshi:xianshis}">{{xianshis}}</div>
    </div> -->
    <!-- 朋友圈 -->
    <div class="pengyouquan">
      <div class="pengyouquan-top">
        <div class="pengyouquan-top-one">
          <div class="pengyouquan-top-one-one"></div>
          <div class="pengyouquan-top-one-two">
            <span v-on:click="xiangji">相机</span>
          </div>
        </div>
        <div class="pengyouquan-top-one-three">liucheng</div>
        <div class="pengyouquan-top-one-foru"></div>
      </div>
      <div class="neirong" v-for="(ietm,index) in array" :key="index">
        <div>{{ietm.id}}</div>
        <div>{{ietm.title}}</div>
        <div>{{ietm.cont}}</div>
      </div>
    </div>
    <!-- 发表 -->
    <div v-bind:class="{fabiao:fab}" v-if="fab!=true" >
      <button v-on:click="dianj">发表</button>
      <input type="text" v-model="shuru" >
    </div>
  </div> 
</template>

<script>
export default {
  name: 'App',
  data:()=> {//函数data这样写就变成了属性名
    return {
      message:"随机点名系统",
      arr:[1,2,3,4,5],
      arrays:["啦啦","哈哈","嘿嘿","呵呵","嘎嘎","哇哇","呜呜"],
      ope:"+",
      sub:0,
      cont:"",
      inp:"啊啊",
      luru:true,
      kaishi: true,
      jieshu: true,
      begins:true,
      sui:true,
      shs:"",
      shuru:"",
      fab:true,
      isActive : true,
      xianshis:"",
      messages:{
        name:"我是messages对象的属性"
      },
      array:[
        {
            id:1,
            title:"这个国家",
            cont:"400万"
    },
     {
            id:2,
            title:"那个国家",
            cont:"300万"
    },
     {
            id:3,
            title:"个国家",
            cont:"200万"
    },
     {
            id:4,
            title:"国家",
            cont:"100万"
    }
    ],
    news: [
        {
          index: 1,
          title: "31省",
          count: 477
        },
        {
          index: 2,
          title: "嫦娥5号",
          count: 477
        },
        {
          index: 3,
          title: "黑龙江",
          count: 477
        },
        {
          index: 4,
          title: "夙愿案",
          count: 477
        }
      ]
    }
  },
  
  methods: {
    test(){
      console.log("我是点击对象")
      
    },
    entering() {//姓名录入
      this.arrays.unshift(this.inp);
    },
     kaish(){//随即开始
      this.begins =setInterval(()=> {
        //console.log(this.arrays)
        this.shs=Math.floor(Math.random()*this.arrays.length)
        this.xianshis=this.arrays[this.shs]
      },500)
     },
     jiesh(){//随机结束
          clearInterval(this.begins)
     },
     xiangji(){//点击相机进入发表页面
      this.fab=false;
     },
     dianj(){
       let tianj={
         id:1,
         title:this.shuru,
         cont:"1000"
       }
      this.array.unshift(tianj)
      console.log(this.array)
     }
  }
  
  
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
.pengyouquan{
  width: 400px;
  height: 500px;
  background: cornflowerblue;

}
.pengyouquan-top{
width: 400px;
height: 200px;
background: cyan;
}
.pengyouquan-top-one{
width: 400px;
height: 50px;
display: flex;
flex-direction: row;
justify-content: space-between;
align-items: center;
}
.pengyouquan-top-one-one{
  width: 30px;
  height: 30px;
  background: chartreuse;
}
.pengyouquan-top-one-two{
  width: 50px;
  height: 50px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;

}
.pengyouquan-top-one-three{
  color: #f5f5f5;
  margin: 130px 0px 0px 160px;

}
.pengyouquan-top-one-foru{
  width: 60px;
  height: 60px;
  background: chocolate;
  margin: -40px 0px 0px 320px;
  border-radius: 10px;
}
.neirong{
  width: 400px;
  height: 200px;
  margin-top: 30px;
  background: cornsilk;
}
.fabiao{
  width: 400px;
  height: 200px;
  background: rgb(240, 159, 38);
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
.active{
  background: rgb(218, 227, 245);
  width: 200px;
  height: 50px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
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
.item {
  width: 400px;
  height: auto;
  background: #f5f5f5;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
.cls {
  color: #2c3e50;
}
.cls1 {
  color: aquamarine;
}
.cls2 {
  color: blue;
}
.cls3 {
  color: bisque;
}
.system{
  width: 300px;
  height: 400px;
  border: cornflowerblue 1px solid;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
.system-top{
  width: 300px;
  height: 50px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.dianming{
   width: 300px;
  height: 50px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}
.xianshi{
  width: 150px;
  height: 100px;
  border: cornflowerblue 1px solid;
  border-radius: 50%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
</style>
