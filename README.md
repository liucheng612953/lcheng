# hello-word

# 总结 git 指令

1. git clone 在 github 上复制
2. git branch \*\* 创建分支
   git branch -a 查看本地所有分支
   git branch -r 查看远程所有分支
3. git checkout \*\* 切换到某某分支
4. git commit -a -m"\*\*\*\*" 提交分支信息
5. git push origin \*\* 上传到指定仓库信息
6. git fetch 把仓库的分支同步拿到本地
7. git pull origin \*\* 在仓库中下载指定的分支到本地
8. git status 查看本地 git 的当前状态（例如：未提交，或者修改过）
9. git add -A 将所有修改提交到暂存区

10. vue 创建新项目：vue create \*\*\* 在 java 文件夹下 Shift+右键开启命令窗口，
    Manually select features ，Babel，In package.json ，n，
    创建好后进入 cd \*\*\*创建的项目名字，npm run serve,运行项目
11. cnpm i 下载依赖
12. vue 创建 router 新项目：vue create \*\*\* 在 java 文件夹下 Shift+右键开启命令窗口，
    Manually select features ，Babel/router，In package.json ，n，
    创建好后进入 cd \*\*\*创建的项目名字，npm run serve,运行项目

# 2020.12.20(下午：vue)

1. vue 语法缩写：v-bind:style="";缩写成:style=""
2. v-on:click=""; 缩写成 @click="";
3. 用 style 动态改变 height 的高度，动态使用数组中的数据，'background-color':'#f40'改变颜色

```
:style="{'height':i.gao+'px','background-color':'#f40'}"
```

4. :key="i.index" key 值是取数组中的唯一索引
5. 微信表情点击，常用列表首位显示

```
<span  v-for="(i , index) in array" :key="index" >-{{i}}-</span>
<button @click="dian(i)" v-for="(i,index) in arr" :key="index">{{i}}</button>
 dian(e){
        this.array=this.array.filter((i)=>{//filter过滤数组，return参数是否一致，重新给this.array数组赋值实现功能
          return !(e==i)
        })
        this.array.unshift(e)//将参数e对应的点击表情添加给常用表情列表数组
      }
```

6. vue 路由的用法，用 js 方式写，编程式导航

```
<div @click="gotoPach('/TiaoZhuan/Child1')">Child1</div>
    <div @click="gotoPach('/TiaoZhuan/Child2')">Child2</div>
    <router-view/>
gotoPach(str){
        this.$router.push(str)//去往上一个页面
        this.$router.replace(str)//去往栈里面的第一个页面
        this.$router.go(-1)//去往上一个页面,也可以是-2，-3
    }
```

路由传参：
gotoPach(str){//参数存入 router 中
const userId = "123"
this.$router.push({name : str , params: {userId}});
        // this.$router.push(str)
}
canshu(){
console.log(this.\$route.params.userId)//获取用 route
}

7. import 和 export 分别是上面意思：import 是引入，export 是输出
8. <router-link></router-link>和<router-view/>分别代表，获取引入得方式，显示电视机

# 2020.12.20(上午：vue)

this 的调用
这里的()=>是 function(){}在 vue 中的写法，如果不换成尖括号写法，this 不能正常调用
也可以在 setInterval 上面 let that=this，用 that 打点属性

```
kaish(){//随即开始
      this.begins =setInterval(()=> {
        //console.log(this.arrays)
        this.shs=Math.floor(Math.random()*this.arrays.length)
        this.xianshis=this.arrays[this.shs]
      },500)
     },
```

# 2020.12.13(下午：Vue)

vue 在 git 上创建新项目：

1. git remote add origin git@github.com:liucheng612953/lcheng.git
2. git branch -M main
3. git push -u origin main

4. 引入 Vue:<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
5. 安装万 node 命令窗口输入 npm，npm -version , cnpm
6. npm 在命令窗口引入：npm install -g cnpm --registry=https://registry.npm.taobao.org
7. 输入 cnpm 看是否报错
8. 输入：cnpm install -g @vue/cli 安装
9. 输入：vue --version
10. 创建 vue 项目命令：vue create 项目名
11. 运行 vue:npm run serve
12. v-bind 鼠标悬停几秒钟查看此处动态绑定的提示信息！

```
<div v-bind:class="[index == 1?cls1:index==2?cls2:index==3?cls3:'',cls]" v-on:click="test">点我</div>
 <div class="item" v-for="item in news" :key="item.index">
      <div
        v-bind:class="[item.index==1?'cls1':item.index==2?'cls2':item.index==3?'cls3':'cls']"
      >{{item.index}}</div>
      <div>{{item.title}}</div>
      <div>{{item.count}}万</div>
    </div>
    <div class=" active " v-for="active in array" :key="active.id">
        <div v-bind:class="[active.index==1?'btn':active.index==2?'btn2':active.index==3?'btn3':'btn4']">{{active.id}}</div>
        <div>{{active.title}}</div>
        <div>{{active.cont}}</div>
  </div>
```

13. v-if v-else if 判断
14. v-for"(itme in arr)" :key="itme.index" for 循环，必须加 key
15. v-on:click onclick 事件
16. v-model 用于表单输入和应用状态的双重绑定
    例如简易的计算加减乘除：

```
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
    <div v-if="ope=='/'">计算结果{{message/sub}}</div>
```

14. template 标签的用法，可以写 v-for 循环，这样子 div 会循环输出，相当于写了很多 div
15. this 直接调用页面中的所有属性 this.message

- Local: http://localhost:8080/
  - Network: http://192.168.0.107:8080/

# npm run serve 运行 vue

vue 中，所有 V 开头的都是指令：v-bind
this 是调用

1. 第一个语法：{{}}

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
