### node.js

node.js是运行在服务端的JavaScript，基于Chrom V8引擎

### npm

npm是node.js的包管理工具

```
查看版本信息：
node -v
npm -v
更新npm到指定版本
npm install npm@x.x.x -g
更新npm到最新的稳定版本
npm install npm@latest -g
```

### webpack

webpack是前端资源模块化管理和打包工具，它可以将很多松散的模块按照依赖和规则打包成符合生产环境部署的前端资源，还可以将按需加载的模块进行代码分割，等到实际需要的时候再异步加载。

webpack是跑在node.js环境下的

webpack4之后不再单独使用，需要webpack-cli

```
全局安装：npm install webpack webpack-cli -g -D
局部安装：npm install webpack webpack-cli -D

模式区分（development, production）
webpack --mode development/production 进行模式切换
development	开发者模式	打包默认不压缩代码
production	生产者模式，上线时使用，压缩代码，默认是此模式

固定入口目录src,与入口默认文件index.js，打包后文件在新增的dist目录下
```



### vue-cli

vue-cli是脚手架工具，其作用就是用配置好的模板迅速搭建起一个项目工程来，省去自己配置webpack配置文件的基本内容。

具体操作就是：

安装好node环境，以及vue-cli后，通过'vue init 模板名 项目名'，然后回答一些配置问题，就可以搭建好一个工程项目。

构建流程：

```
前提是安装好了node.js
1、使用npm全局安装vue-cli
npm install -g vue-cli
2、安装完成后在自己的工作空间内
vue init webpack vue-demo
3、切换到项目目录下
cd vue-demo 
npm run dev
```

目录结构：

```
build里面是一些操作文件，使用npm run xx时执行的就是这里的文件
config 配置文件，执行文件需要的配置信息
src 资源文件，所有的组件以及所有的图片都在这个文件夹下
node-modules 项目依赖包
static 静态资源
package.json 依赖包的json文件
```



最后，在我们项目打包后，我们的项目就和node.js、vue-cli、webpack、npm都无关了，打包后的项目就是一个单纯的项目静态资源包，我们只是利用这些工具在开发，让我们的开发高效起来。

