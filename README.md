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


