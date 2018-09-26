# Egg

### Egg.js是什么？

**Egg.js为企业级框架和应用而生**，是一个基于Node开发的服务器框架，由阿里团队打造而成。

### Egg.js 与 Koa

Egg继承于Koa，Koa已经是一个非常优秀的框架了，但对于一个企业级应用来说，它还不够完善，而Egg选择了Koa作为基础框架，在它的模型基础上，进一步对它进行增强。可以理解为Egg就是Koa的升级版本，更加的完善。

![](http://qiniu.xl686.com/egg.png)

### 快速入门

Egg.js是一个基于Node开发的框架，所以Node环境是必不可少的。大家可以到[node](https://nodejs.org)的官网中进行下载安装，本人比较建议下载安装长期维护版本，更加的稳定安全。

#### 快速初始化

Egg提供官网的脚手架，可以自己安装使用。

```
$ npm i egg-init -g						   //全局安装egg脚手架
$ egg-init project-name --type=simple		//创建项目
$ cd project-name						  //进入项目	
$ npm install		   					  //安装依赖文件
```

启动项目

```
$ npm run dev
$ open localhost:7001
```

### 目录结构

打开使用官方脚手架工具生成的项目，可以看到结构目录如下

```javascript
projec-name
├── app
│   ├── controller
│   │   └── home.js
│   └── router.js
├── config
│  	├── plugin.js
|   └── config.default.js
├── test
│   └── app
│		└── controller
│			└── home.test.js
└── package.json
```

如上，脚手架初始化项目的目录：

- `app/router.js`用于配置URL路由规则
- `app/controller/**`用于解析用户的输入，处理后返回相应的结果
- `config/plugin.js`用于配置需要加载的的插件
- `config/config.default.js`用于编写配置文件
- `test`单元测试

通常情况下，我们会在里面添加几个文件

- `app/public/**`用于放置静态资源，具体参见内置插件 [egg-static](https://github.com/eggjs/egg-static)
- `app/view/**`用于放置模板文件，具体参见内置插件 [egg-view-nunjucks](https://github.com/eggjs/egg-view-nunjucks)
- `app/service/**` 用于编写业务逻辑层

### 框架的内置对象

由于`Egg.js`是底层框架是`Koa`，所以Egg继承了`Koa`的4个对象（`Application,Context,Request,Response`)以及框架扩展的一些对象（`Controller,Service,Helper,Config,Logger`）。

