# patch-package sprint

[patch-package doc](https://github.com/ds300/patch-package)

## Install

```shell
yarn add --dev patch-package postinstall-postinstall

# or
npm i --save-dev patch-package
```

## Set-up

修改 package.json

```diff
 "scripts": {
+  "postinstall": "patch-package"
 }
```

## Usage

1. 在本地修复 bug（直接修改 node_modules 下的代码）。

2. 使用 patch-package 创建补丁文（默认在 patches/* 下）。

```shell
## some-package 是要修复包的保命，本示例项目用的 lodash（即 npx patch-package lodash）
npx patch-package <some-package>
```

3. 提交代码 patches 的代码。

4. 应用 patches

```shell
# 因为 package.json 配置了 "postinstall": "patch-package", 在 yarn 或 npm install 完成后会自动应用。

# 手动应用所有 patches
npx patch-package
```
