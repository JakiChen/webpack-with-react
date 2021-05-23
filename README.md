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
4. 现在，您在package.json文件中的依赖项将具有以下内容：

````json
"dependencies": {
   "react": "^17.0.1",
   "react-dom": "^17.0.1"
 }
````
