### 利用 babel 来编译 es6 代码

```bash
pnpm i core-js @babel/core @babel/preset-env @babel/plugin-transform-runtime
```

> @babel/preset-env 可以根据配置的目标浏览器或者运行环境来自动将 ES2015+的代码转换为 es5。需要注意的是，我们设置"modules": false，否则 Babel 会在 Rollup 有机会做处理之前，将我们的模块转成 CommonJS，导致 Rollup 的一些处理失败。

> 为了解决多个地方使用相同代码导致打包重复的问题，我们需要在.babelrc 的 plugins 里配置@babel/plugin-transform-runtime，同时我们需要修改 rollup 的配置文件：
