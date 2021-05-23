# 从零开始使用React和Babel设置Webpack 5 [2021]
 
创建自己的Webpack配置听起来对中级React开发人员来说都是吓人的。但是解决问题的最好方法就是直面它！这个博客将帮助您为下一个React项目使用React和Babel设置自己的基本Webpack捆绑器！它也适合试图了解Webpack基础知识，Webpack的设置方式或实际情况的人们。因此，让我们开始吧！

### 步骤1（设置文件夹和下载依赖项）
1. 首先创建一个文件夹，然后根据需要命名。我叫我的 `react-webpack`。
2. 进入文件并初始化程序包管理器。`-y` 代表在命令行中提出的所有一般开发问题的“是”。

```dash
npm init -y
```
3. 接下来，我们将安装react依赖项。

```
npm i react react-dom
```
4. 现在，您在 `package.json` 文件中的依赖项将具有以下内容：

````json
"dependencies": {
   "react": "^17.0.1",
   "react-dom": "^17.0.1"
 }
````
5. 接下来，我们将安装dev依赖项和加载程序
```
npm i -D @babel/core @babel/preset-env @babel/preset-react babel-loader file-loader css-loader style-loader webpack webpack-cli html-webpack-plugin
````
6. 这就是devDependencies的样子 `package.json`：
```json
"devDependencies": {
   "@babel/core": "^7.13.10",
   "@babel/preset-env": "^7.13.10",
   "@babel/preset-react": "^7.12.13",
   "babel-loader": "^8.2.2",
   "css-loader": "^5.1.3",
   "file-loader": "^6.2.0",
   "html-webpack-plugin": "^5.3.1",
   "style-loader": "^2.0.0",
   "webpack": "^5.27.0",
   "webpack-cli": "^4.5.0",
   "webpack-dev-server": "^3.11.2"
 }
```

### 步骤2（使用Babel设置Webpack）
### 步骤3（设置react文件夹）
### 步骤4（运行应用）
### 奖励：优化！
