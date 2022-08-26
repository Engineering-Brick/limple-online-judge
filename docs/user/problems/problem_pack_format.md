# Limple OJ 用户文档 - 题目 - 题目包格式

欢迎阅读 Limple OJ 用户文档 - 题目 - 题目包格式!

Limple OJ 使用“题目包”机制处理和存储题目。

## 1. 题目包

题目包是一个 `*.zip` 格式的压缩包，应包含一道题目的所有信息。

其结构应如下：

```
*.zip
    n.in
    n.ans
    ......
    body.md
    checker.cpp
    description.json
```

注意， 压缩包下应直接包含文件，而不是包含子目录。

题目包中除 `description.json` 文件外的所有文件都可以使用其他文件名。

## 2. `description.json` 文件

此文件使用 `JSON` 格式, 描述了题目的编号、标题、题面文件、数据点等信息。

下面是一个合法的 `description.json` 文件举例：

```json
{
    "id": "P1",//题目 ID
    "title": "A+B Problem",//题目标题
    "body": "body.md",//题面文件名
    "judge_type": "default",//评测类型，目前只支持 default(经典题) 一种，未来将会支持交互题等更多类型......
    "judge_info": { //评测信息(以 default 类型为例)
        "checker": "checker.cpp",//检查器文件名（目前检查器仅支持C++17）
        "cases":[//测试点信息
            {
                "id": 1,//测试点标识符，每个测试点的标识符应唯一
                "memory": 128,//最大内存，单位为MiB
                "time": 1000,//最大时间，单位为ms
                "input": "1.in",//输入文件名
                "output": "1.out"//输出文件名
            },
            {
                "id": 2,
                "memory": 128,
                "time": 1000,
                "input": "2.in",
                "output": "2.out"
            }
        ],
        "subtasks":[//子任务信息
            ;
        ]
    }
}
```

## 3. 检查器