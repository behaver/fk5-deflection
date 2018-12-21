# FK5Deflection

[![GitHub license](https://img.shields.io/badge/license-MIT-brightgreen.svg)](#) [![npm version](https://img.shields.io/npm/v/react.svg?style=flat)](https://www.npmjs.com/package/@behaver/fk5-deflection) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#)

## 简介

FK5Deflection 是一个用于计算 VSOP 动力学坐标与 FK5 坐标之间的偏差的组件

## 安装

通过 npm 安装，在你的 node 项目目录下执行：

`npm i --save @behaver/fk5-deflection`

安装完成后，调用即可：

`const FK5Deflection = require('@behaver/fk5-deflection');`

## 用例

```js
const FK5Deflection = require('@behaver/fk5-deflection');
const { JDateRepository } = require("@behaver/jdate");
const { SphericalCoordinate3D } = require('@behaver/coordinate');

let FK5D = new FK5Deflection({
  time: new JDateRepository(18, 'j2000'),
  sc: new SphericalCoordinate3D(230043, 1.123, 1.55),
});

let res = FK5D.get();
```

## API

`constructor(options)`

构造函数:

* options.time   计算时间
* options.sc     天体球坐标 (距离单位：AU)
* options.system 坐标系统

`get()`

获取 FK5 修正值对象

`get time()`

获取计算时间

`set time(time)`

设置计算时间

## 许可证书

The MIT license.