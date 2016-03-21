# gulp

```
gulp是目前前端开发很火的一个自动化构建工具。
觉得类似于Makefile。
目前正在学习中。
```
[gulp 中文网](http://www.gulpjs.com.cn/)

## 安装

1. 全局安装 gulp：

```bash
$ npm install --global gulp
```

2. 作为项目的开发依赖（devDependencies）安装：

```bash
$ npm install --save-dev gulp
```

**两处都要安装**

3. 在项目根目录下创建一个名为 gulpfile.js 的文件：

```javascript
var gulp = require('gulp');

gulp.task('default', function() {
  // 将你的默认的任务代码放在这
});
```

4. 运行 gulp：

```bash
$ gulp
```

默认的名为 default 的任务（task）将会被运行，在这里，这个任务并未做任何事情。

想要单独执行特定的任务（task），请输入 gulp <task> <othertask>。

## gulp API 

#### gulp.src(globs[, options])

简单理解就是读取文件，然后通过.pipe传送给其他插件。

```javascript
gulp.src('client/templates/*.jade')
  .pipe(jade())
  .pipe(minify())
  .pipe(gulp.dest('build/minified_templates'));
```

#### gulp.dest(path[, options])

简单理解就是写文件

上面的例子中就是读了写文件，然后写到另一个文件夹中了。

如果文件夹不存在，将自动创建。

#### gulp.task(name[, deps], fn)

定义一个使用 Orchestrator 实现的任务（task）。

#### gulp.watch(glob[, opts, cb])

监视文件改动


## 前端常用gulp插件

[前端构建之gulp与常用插件](http://www.mamicode.com/info-detail-517085.html)

[gulp如何压缩html当中的js和css代码？](https://segmentfault.com/q/1010000004175372?_ea=517311)

No.3、del

Links：https://www.npmjs.com/package/del

作用：删除文件/文件夹

No.1、run-sequence

Links: https://www.npmjs.com/package/run-sequence

作用：让gulp任务，可以相互独立，解除任务间的依赖，增强task复用


No.8、gulp-util

Links: https://www.npmjs.com/package/gulp-util

作用：gulp常用的工具库

No.9、gulp-uglify

Links: https://www.npmjs.com/package/gulp-uglify

作用：通过UglifyJS来压缩JS文件

No.11、gulp-less

Links：https://www.npmjs.com/package/gulp-less

作用：将less预处理为css

推荐指数：★★★★

No.12、gulp-sass

Links：https://www.npmjs.com/package/gulp-sass

作用：将sass预处理为css

No.14、gulp-minify-css

Links：https://www.npmjs.com/package/gulp-minify-css

作用：压缩css。


grunt

sass


