# Web Framework

A component-based orchestration web framework

# pnpm monorepo

## 模块之间依赖

```
pnpm add @krill/xxx -Dw
// for exp
pnpm add @krill/web-framework-utils -Dw
```

## husky 配置

```
husky install

# pre-commit
npx --no-install lint-staged

#commit-msg
npx --no-install commitlint --edit ""
```

# 开发配置

1. 开发时需配置 config.json，方式：从 packages/container/config.default.json copy 一份出来，并在其内加上如下内容：

```
{
  "server": {
    "port": 8888
  },
  "webSocketServer": {
    "enabled": true,
    "port": 9999,
    "reloadAsPluginUpdated": true
  },
  "plugins": {
    "component": ["/home/ximenchuixue/work/web-framework-plugins/components/*/dist"],
    "library": ["/home/ximenchuixue/work/web-framework-plugins/libraries/*/dist"]
  },
  "storyboards": ["/home/ximenchuixue/work/web-storyboards/console/storyborad.json"]
}
```

2 运行`pnpm build`
3 运行 `pnpm start`

# 发布

pnpm monorepo 默认的能力是：依赖安装、运行、构建。
缺失的能力是版本管理，其可用 changeset 补充
使用文档：https://pnpm.io/zh/using-changesets

```
$ pnpm add -DW @changesets/cli
$ pnpm changeset init
```

## changeset 一个注意的问题

主干分支是 main 而不是 master

# 语义化版本管理 semver

https://semver.org/
语义化的版本控制（Semantic Versioning），简称语义化版本，英文缩写为 SemVer。
版本：语义化版本格式：主版本号.次版本号.修订号（MAJOR.MINOR.PATCH）mmp

# npm 403

将http://registry.npm.taobao.org 淘宝镜像切到

```
npm config set registry=https://registry.npmjs.org/
```

发布之后再切换淘宝镜像

```
npm config set registry=https://registry.npm.taobao.org/
npm config get registry
```

# git 改变远程仓库地址
```
git remote set-url origin git@github.com:mshmyw/krill-frame.git
```
