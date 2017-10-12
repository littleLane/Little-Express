# Express

基于 ` Node.js ` 平台，快速、开发、极简的 ` web ` 开发框架。

## 安装 ` Express `

> ` npm install express --save `

## 安装生成器

> ` npm install express-generator -g `

检测生产器是否安装成功

```javascript
$ express -h

  Usage: express [options] [dir]

  Options:

    -h, --help          output usage information
    -V, --version       output the version number
    -e, --ejs           add ejs engine support (defaults to jade)
        --hbs           add handlebars engine support
    -H, --hogan         add hogan.js engine support
    -c, --css <engine>  add stylesheet <engine> support (less|stylus|compass|sass) (defaults to plain css)
        --git           add .gitignore
    -f, --force         force on non-empty directory
```

## 利用生成器生产项目 ` myapp `

```javascript
$ express myapp

   create : myapp
   create : myapp/package.json
   create : myapp/app.js
   create : myapp/public
   create : myapp/public/javascripts
   create : myapp/public/images
   create : myapp/routes
   create : myapp/routes/index.js
   create : myapp/routes/users.js
   create : myapp/public/stylesheets
   create : myapp/public/stylesheets/style.css
   create : myapp/views
   create : myapp/views/index.jade
   create : myapp/views/layout.jade
   create : myapp/views/error.jade
   create : myapp/bin
   create : myapp/bin/www
```

然后安装所有依赖包

```
$ cd myapp 
$ npm install
```

启动这个应用（` MacOS ` 或 ` Linux ` 平台）

```
$ DEBUG=myapp npm start
```

` Windows ` 平台

```
> set DEBUG=myapp & npm start
``` 

然后在浏览器中打开 http://localhost:3000/ 网址就可以看到这个应用了.

## 项目目录

```
.
├── app.js              # 项目的启动文件
├── bin                 # 存放可执行文件
│   └── www
|—— node_modlues        # 存储工程信息以及模块依赖
├── package.json        # 存放 package.json 中安装的模块，添加依赖的模块并安装后，存放在这个文件里面
├── public              # 存放 image、css、js等文件
│   ├── images
│   ├── javascripts
│   └── stylesheets
│       └── style.css
├── routes              # 存放路由文件
│   ├── index.js
│   └── users.js
└── views               # 存放视图文件
    ├── error.jade
    ├── index.jade
    └── layout.jade

7 directories, 9 files
```

## 四大对象

- 1、` Application ` 对象

> 创建一个 ` Express ` 应用，通过 ` app ` 对象，可以实现定向 ` HTTP ` 请求，配置中间件、渲染 ` HTML `、配置模板等

- 2、` Request ` 对象

> ` Request ` 对象代表 ` HTTP ` 请求，以及请求中的查询字符串、请求体、` HTTP ` 头等

- 3、` Response ` 对象

> 对 ` Node.js http.ServerResponse ` 对象的扩展

- 4、` Router ` 对象

> 一个独立的中间件和路由实例。你可以把它想象成一个 ”迷你应用程序“，只能够执行中间件和路由的功能。

## 中间件

- 1、概述

> 在收到请求后和发送响应之前这个阶段执行的一些函数，写一个中间件函数通常由名为 ` next ` 的变量来表示

- 2、功能

> 执行任何代码
> 对请求和响应对象进行更改
> 调用堆栈中的下一个中间件