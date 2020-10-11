# 安装和配置 jest+vue/test-utils 的简易教程



1. 从 nodejs.org 中下载 nodejs，完成安装。
2. 使用 npm install --global vue-cli 指令全局安装 vue-cli。
3. 使用 vue init webpack "项目名称" 新建项目。
4. 新建项目时引入 jest。
5. cd 到项目目录中，使用 npm install @vue/test-utils 指令安装 vue/test-utils 模块。
6. 在 package.json 中定义一个单元测试的脚本。

```
{
  "scripts": {
    "test": "jest"
  }
}
```
7.配置 jest.conf.js 配置文件：
```
import { mount } from '@vue/test-utils'
import Component from './component'

describe('Component', () => {
  test('是一个 Vue 实例', () => {
    const wrapper = mount(Component)
    expect(wrapper.isVueInstance()).toBeTruthy()
  })
})
```
8.使用 npm run unit 启动单元测试命令。
+ 常见的断言
```
//普通匹配器

expect().toBe()//测试是否完全相等
expect().toEqual//检查某个对象的值
expect().not.toBe()

//布尔值匹配器
expect().toBeNull()//布尔值匹配器
expect().toBeTruthy//toBeTruthy 匹配任何 if 语句为真
expect().toBeFalsy//toBeFalsy 匹配任何 if 语句为假

//数字匹配器
expect().toBeGreaterThan//大于
expect().toBeLessThan//小于
```