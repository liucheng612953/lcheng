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
