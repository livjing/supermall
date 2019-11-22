# supermall

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

### 项目笔记
#### 1. 创建
```
vue create supermall
```
#### 2. 使用git
* 2.1 github上 new repository
* 2.2 本地 clone url
* 2.3 git status
红色显示哪些文件没被commit
```
supermall>git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .browserslistrc
        .gitignore
        README.md
        babel.config.js
        package-lock.json
        package.json
        postcss.config.js
        public/
        src/

nothing added to commit but untracked files present (use "git add" to track)
```
* 2.4 git add 文件名
git add . 添加所有上述文件
```
supermall>git add .
warning: LF will be replaced by CRLF in .browserslistrc.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in .gitignore.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in babel.config.js.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in package-lock.json.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in package.json.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in postcss.config.js.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in public/index.html.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in src/App.vue.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in src/components/HelloWorld.vue.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in src/main.js.
The file will have its original line endings in your working directory

```
* 2.5 git commit -m '初始化项目'
这时只是提交到了本地
```
supermall>git commit -m '初始化项目'
[master a96a794] '初始化项目'
 13 files changed, 11062 insertions(+)
 create mode 100644 .browserslistrc
 create mode 100644 .gitignore
 create mode 100644 README.md
 create mode 100644 babel.config.js
 create mode 100644 package-lock.json
 create mode 100644 package.json
 create mode 100644 postcss.config.js
 create mode 100644 public/favicon.ico
 create mode 100644 public/index.html
 create mode 100644 src/App.vue
 create mode 100644 src/assets/logo.png
 create mode 100644 src/components/HelloWorld.vue
 create mode 100644 src/main.js
```
* 2.6 git push
提交到服务器
```
supermall>git push
Enumerating objects: 20, done.
Counting objects: 100% (20/20), done.
Delta compression using up to 8 threads
Compressing objects: 100% (16/16), done.
Writing objects: 100% (19/19), 111.75 KiB | 5.08 MiB/s, done.
Total 19 (delta 0), reused 0 (delta 0)
To https://github.com/184622608/supermall.git
   f9992b9..a96a794  master -> master

```
PS:如何将当前文件夹远程关联仓库
```
git remote add origin 仓库地址
git push -u origin master
```

### 新项目划分目录结构

src
  * common 公共的JS文件(如:常量)
    -- const.js 公共常量
    -- utils.js 公共方法
  * assets  资源
      -- css
      -- img
  * components 
    -- common 公共组件
    -- content 当前项目相关组件
  * views   大的视图(首页,分类,购物等)
    -- home
    -- category
  * router 路由
  * store 状态管理vuex
  * network 网络封装(如: axios)

### 统一CSS样式
很多控件在不同的浏览器会显示不同的样式
引入CSS(normalize)文件,让其显示样式统一
github normalize.css
assets/css/
  -- normalize.css
  -- base.css       // @import "./normalize.css";

App.vue中引入
```
<style>
  @import "assets/css/base.css";

</style>
```
```
:root {  // -> 伪类, 获取根元素html
  --color-text: #666;   // 定义变量
  --color-high-text: #ff5777;
  --color-tint: #ff8198;
  --color-background: #fff;
  --font-size: 14px;
  --line-height: 1.5;
}

在其它样式中使用{
  
  font-size: var(--font-size);
}

```

### 添加 vue.config.js 和 .editorconfig
CLI3 添加 别名
根目录下新建 
vue.config.js
```
module.exports = {
  configureWebpack:{
    resolve:{
      alias:{
        'assets': '@/assets',
        'common': '@/common',
        'components': '@/components',
        'network': '@/network',
        'views': '@/views',
      }
    }
  }
};

```

.editorconfig
```
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true

```

添加之前写过的TabBar组件
components
  * common  公共组件
    -- tabbar
      -- TabBar.vue
      -- TabBarItem.vue
  * content 当前业务相关
    -- mainTabBar
      -- MainTabBar.vue


使用MainTabBar
```
<template>
  <div id="app">
    <main-tab-bar></main-tab-bar>
  </div>
</template>

<script>
  import MainTabBar from "components/content/mainTabBar/MainTabBar";

  export default {
    name: 'app',
    components: {
      MainTabBar
    }
  }
</script>
```

MainTabBar中使用router, 所以安装它
npm install vue-router --save

### 使用router
src/router/index.js
```
import Vue from 'vue'
import VueRouter from "vue-router"

// 1. 安装插件
Vue.use(VueRouter);

const routes = [
];

// 2. 创建router
const router = new VueRouter({
  routes,
  mode: 'history'
});

export default router
```
main.js中挂载 router
```
import router from './router'

new Vue({
  render: h => h(App),
  router
}).$mount('#app')
```

配置router映射关系
```
const routes = [
  {
    path: '',
    redirect: '/home'
  },
  {
    path: '/home',
    component: Home
  },
  {
    path: '/category',
    component: Category
  },
  {
    path: '/cart',
    component: Cart
  },
  {
    path: '/profile',
    component: Profile
  }
];
```
使用router
App.vue
```
  // 3 使用并显示
  <router-view></router-view>
  <main-tab-bar></main-tab-bar>

  // 1 导入
  import MainTabBar from "components/content/mainTabBar/MainTabBar";

  // 2 注册
  export default {
    components: {
      MainTabBar
    }
  }
```

## Vue的默认小图标问题
修改public/.ico 和 index.html
```
<link rel="icon" href="<%= BASE_URL %>logo.png">
BASE_URL 动态获取当前文件所在的路径
```
打包后是没有这种语法的
```
npm run build
打开dist/index.html
href=/logo.png
```

id  一处使用
class 多处使用
