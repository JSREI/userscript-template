# UserScript Template 

# 一、这是什么

使用`NodeJS`+`WebPack`开发油猴脚本的方案，用于提升油猴开发体验，一个`JavaScript`文件几千行来回改本人真的有点顶不住......

# 二、如何使用

在当前仓库选择“Use this template” --> “Create a new repository”，创建一个新的仓库： 

![image-20230816233501101](README.assets/image-20230816233501101.png)

选择存放的位置以及设置仓库名字等等：

![image-20230816235634094](README.assets/image-20230816235634094.png)

仓库创建好了之后修改`package.json`文件，把相关字段替换为你自己的，比如名字、作者、仓库地址等等：

```js
{
  "name": "userscript-foo",
  "version": "0.0.1",
  "main": "index.js",
  "repository": "https://github.com/JSREI/userscript-template.git",
  "scripts": {
      // ... 
  },
  "author": "CC11001100 <CC11001100@qq.com>",
  "license": "MIT",
  "devDependencies": {
      //...
  }
}
```

在`userscript-headers.js`文件中存放的是默认的油猴头文件：

```
// ==UserScript==
// @name         ${name}
// @namespace    ${repository}
// @version      ${version}
// @description  ${description}
// @document     ${document}
// @author       ${author}
// @match        *://*/*
// @run-at       document-start
// ==/UserScript==
```

`${name}`这种是支持的一些变量，在编译的时候会从`package.json`中获取对应的值替换掉。

然后就可以开心的写代码了，当你需要测试的时候，执行：

```bash
npm run watch
```

然后把`./dist/index.js`中的文件头复制到你的油猴中：

![image-20230817000716664](README.assets/image-20230817000716664.png)

并在最后添加一行引入编译后的文件：

```js
// @require    file://D:/workspace/userscript-template/dist/index.js
```

比如一个开发时使用的油猴脚本的例子，油猴中不实际配置内容，而是使用require指向我们build后的文件，这样当修改完代码热加载编译的时候浏览器中引用的JS也是最新的：

```js
// ==UserScript==
// @name         userscript-foo
// @namespace    https://github.com/JSREI/userscript-template.git
// @version      0.0.1
// @description  
// @document     
// @author       CC11001100 <CC11001100@qq.com>
// @match        *://*/*
// @run-at       document-start
// @require    file://D:/workspace/userscript-template/dist/index.js
// ==/UserScript==
(() => {})();
```

当你需要发布的时候：

```bash
npm run build
```

然后把`./dist/index.js`文件拿去发布即可。







