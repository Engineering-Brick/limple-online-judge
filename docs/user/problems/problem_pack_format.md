# Limple OJ 用户文档 - 题目 - 题目包格式

欢迎阅读 Limple OJ 用户文档 - 题目 - 题目包格式!

Limple OJ 使用“题目包”机制处理和存储题目。

## 1. 题目包

题目包是一个 `*.zip` 格式的压缩包，应包含一道题目的所有信息。

其结构应如下：

```
*.zip
    *.in
    *.ans
    ......
    *.md
    description.json
```

注意， 压缩包下应直接包含文件，而不是包含子目录。

题目包中除 `description.json` 文件外的所有文件都可以使用其他文件名。

## 2. `description.json` 文件

此文件描述了题目的编号、标题、题面文件、数据点等信息。

下面是一个合法的 `description.json` 文件举例：

```json
{
    "id": "P1",//题目 ID
    "title": "A+B Problem",//题目标题
    "body": "body.md"//题面文件名
    //施工中。。。。。。
}
```