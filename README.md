
# babel 
## babel 全局安装
`# cnpm install bable-cli --global`

## 项目依赖安装
`# cnpm install babel-cli --save`

- 执行 babel-cli 
`# ./node_modules/.bin/babel script.js -o script-compile.js`
`# ./node_modules/.bin/babel script.js --out-file script-compile.js`

- 编译目录中的文件
`# ./node_modules/.bin/babel src --out-dir build`

- 监听文件变化
`# ./node_modules/.bin/babel src --watch --out-dir build`

# npm run build 配置
- package.json
```
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "build": "babel src --watch --out-dir build"
}
```
- npm run build

# babel-plugin-transform-es2015-arrow-functions 插件


# preste 预设
> babel 插件集合

- babel-preset-es2015
- babel-preset-react

## babel-preset-es2015
1. 安装es2015预设 : 
`cnpm install babel-preset-env --save-dev`

2. .bablerc
```
{
  "presets": [
    "env"
  ]
}
```
3. npm run build

## babel-preset-react
`cnpm install babel-preset-react --save`
1. 安装 react 预设 : 
`cnpm install babel-preset-react --save-dev`

2. .bablerc
```
{
  "presets": [
    "env","react"
  ]
}
```
3. `npm run build`

# babel 与 gulp
1. `cnpm install gulp gulp-babel --save-dev`
2. gulpfile.js 配置文件
```
var gulp = require('gulp');
var babel = require('gulp-babel');
gulp.task('default', ()=>{
  return gulp.src('src/*.js')
    .pipe(babel())
    .pipe(gulp.dest('build'))
});
```
3. gulp