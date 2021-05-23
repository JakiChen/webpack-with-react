# 从零开始使用React和Babel设置Webpack 5 [2021]
 
创建自己的Webpack配置听起来对中级React开发人员来说都是吓人的。但是解决问题的最好方法就是直面它！这个博客将帮助您为下一个React项目使用React和Babel设置自己的基本Webpack捆绑器！它也适合试图了解Webpack基础知识，Webpack的设置方式或实际情况的人们。因此，让我们开始吧！

### 步骤1（设置文件夹和下载依赖项）
- 首先创建一个文件夹，然后根据需要命名。我叫我的 `react-webpack`。
- 进入文件并初始化程序包管理器。`-y` 代表在命令行中提出的所有一般开发问题的“是”。

```dash
npm init -y
```
- 接下来，我们将安装 `react` 依赖项。

```
npm i react react-dom
```
- 现在，您在 `package.json` 文件中的依赖项将具有以下内容：

````json
"dependencies": {
   "react": "^17.0.1",
   "react-dom": "^17.0.1"
 }
````
- 接下来，我们将安装dev依赖项和加载程序
```
npm i -D @babel/core @babel/preset-env @babel/preset-react babel-loader file-loader css-loader style-loader webpack webpack-cli html-webpack-plugin
````
- 这就是devDependencies的样子 `package.json`：
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
- 接下来，我们将创建一个名为的文件`.babelrc`，该文件会将我们的`React` 代码从`jsx`转换为常规`js`。我们需要包括以下预设：
```json
{
   "presets": [
       "@babel/preset-env",
       "@babel/preset-react"
   ]
}
```
- 接下来，我们将创建webpack文件。我们将其命名 `webpack.config.js`。此`webpack`文件夹实质上在节点环境中运行，而不在浏览器中运行。因此，我们可以在此处编写原始js代码。
```javascript
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  // Where files should be sent once they are bundled
 output: {
   path: path.join(__dirname, '/dist'),
   filename: 'index.bundle.js'
 },
  // webpack 5 comes with devServer which loads in development mode
 devServer: {
   port: 3000,
   watchContentBase: true
 },
  // Rules of how webpack will take our files, complie & bundle them for the browser 
 module: {
   rules: [
     {
       test: /\.(js|jsx)$/,
       exclude: /nodeModules/,
       use: {
         loader: 'babel-loader'
       }
     },
     {
       test: /\.css$/,
       use: ['style-loader', 'css-loader']
     }
   ]
 },
 plugins: [new HtmlWebpackPlugin({ template: './src/index.html' })],
}
```
> 了解 `webpack.config.js`
> - 在 `output` 我们提到的文件打包后应该将文件发送到哪里。
  path提到要创建的目录名称，所有捆绑文件将存储在该目录中。我们已将文件夹命名为dist，这是一种常见的做法。
这filename是我们为将在webpack运行后创建的新捆绑文件设置的名称，这很神奇（基本上将所有js代码捆绑到一个文件中）。
devServer 用于快速开发应用程序，这与生产模式相反，生产模式要花更多的时间来构建应用程序，因为它会缩小文件，这在开发模式下不会发生。

通过port我们可以设置我们选择的端口号。我已将其设置为3000。
watchContentBase 在任何文件中进行任何更改时，将触发整页重新加载。默认情况下，此功能处于禁用状态。
module 是您通过捆绑文件规则的地方。

test是我们提到文件扩展名的地方，它需要由特定的加载程序作为目标。所有.js或.jsx文件都需要由babel loader捆绑。
exclude 是我们提到捆绑程序需要忽略的文件的地方。
文件css也是如此。重要的是要注意，use :['style-loader', 'css-loader']需要按照确切的顺序来编写数组。
当webpack捆绑css文件时，这是它的顺序：
它首先运行css-loader将css文件转换为通用js的。
然后运行style-loader它，将css作为字符串提取到文件中。
最后，我们添加一个plugin名为HtmlWebpackPlugin的文件，以确保Webpack知道要运行该应用程序要遵循的html文件模板。
### 步骤3（设置react文件夹）
### 步骤4（运行应用）
### 奖励：优化！
