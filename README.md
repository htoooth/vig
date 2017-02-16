# vig [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-image]][daviddm-url] [![Coverage percentage][coveralls-image]][coveralls-url]

## 关于vig

是一个专注于Web业务逻辑的框架，主要关心：

1. 精减Web业务处理的代码
2. 简化常规Web业务的处理
3. 加速项目的开发
4. 是一个简化Web业务处理的Web框架
5. 将Web的业务逻辑标准化，可重用化是vig的主要目标

目标是：

1. 模块化(Modular)
2. 可插件化(Pluggable)
3. 可重入化(Reenterable)
4. 可集成化(Integratable)

# 为什么要使用vig，而不直接使用Sailsjs等框架

Sailsjs的一些问题是这个框架出现的主要原因。

Sailsjs简化了很多Web业务，提供了很多有价值的模块，但是Sailsjs本身的集成度过高，不利于软件的模块化与项目的扩展.

因此，才有了vig的出现。

vig保留了Sailsjs里有价值的部分，去除了一些不安全的东西，并让开发更加的灵活，同时提供了很多新的功能。


# 功能列表

1. 简化的路由机制
2. 简洁，而强大的数据输入校检
3. 方便的权限验证功能
4. 框架内的事件机制
5. 实用的VIG API规范
6. 简单的文件上传机制
7. 简单的模型定义方式（基于waterline）
8. 统一的错误处理机制（基于Errorable）


## 快速上手

1、创建一个test.js文件

```sh
vi test.js
```

2、添加如下代码

```js
var app = require('express')();
var vig = require('vig');
vig.init(app);
vig.addHandler(app, {
  prefix: '/demo',
  urls: ['/', '/hello'],
  routers: {
    get: function (req, res) {
      res.send('Hello world!');
    }
  }
});

app.listen(10000, function () {
  console.log('server running on http://localhost:1000');
});
```

3、执行

```sh
npm install --save vig
npm install --save express
```

4、运行

```
node test
```

## 教程

[第一章 最简服务器创建](./demo/chapter-1)   

[第二章 URL路由（别名与前缀）机制](./demo/chapter-1)   

[第三章 vig的http方法机制详解](./demo/chapter-2)  

[第四章 输入数据的校验与提取](./demo/chapter-3)  

[第五章 输入数据的校验与提取（二）](./demo/chapter-4)  

[第六章 输入数据的校验与提取（三）](./demo/chapter-5)  

[第七章 基于waterline操作数据库与模型](./demo/chapter-6)  

[第八章 在vig中进行错误处理](./demo/chapter-7)   

[第九章 在vig中进行文件处理（未完成）](./demo/chapter-8)    

[第九章 应用权限机制（未完成）](./demo/chapter-9)    

[第九章 错误处理机制（未完成）](./demo/chapter-10)    


## 关于async/await支持的几点说明

vig对async/await的支持依赖于用户的开发环境本身，与vig框架无关。  
但是开发者需要注意的是:

1. async/await无法实现对事件的支持,所以回调函数与async/await是不同的。
2. 回调函数不会消失，async/await也无法适用于所有的场景

所以在使用vig框架时需要注意事件与IO回调的区别。  

下面再将事件与常规的IO调用的差别说明一下。

1. IO的调用本身也是事件。  
2. IO调用本身也是可以不定期的，比如网络IO。  
3. 对于时间与任务明确的IO调用，推荐async/awati，比如数据库访问，文件访问等。  
4. 对于不明确的事件应该使用回调，比如有些网络IO，一些硬件的IO事件，如键盘事件，鼠标事件等。  
5. async/await无法取代回调函数  

## 安装

```sh
$ npm install --save vig
$ yarn add vig
```

## 教程与文档

[教程与文档](./docs/README.md);

## 项目地址

https://github.com/calidion/vig


## License

Apache-2.0 © [calidion]()


[npm-image]: https://badge.fury.io/js/vig.svg
[npm-url]: https://npmjs.org/package/vig
[travis-image]: https://travis-ci.org/calidion/vig.svg?branch=master
[travis-url]: https://travis-ci.org/calidion/vig
[daviddm-image]: https://david-dm.org/calidion/vig.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/calidion/vig
[coveralls-image]: https://coveralls.io/repos/calidion/vig/badge.svg
[coveralls-url]: https://coveralls.io/r/calidion/vig


