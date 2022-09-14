---
title: Unity事件注册于呼叫事件
date: 2022-09-12 00:00:32
tags: 
- 导航
- 事件
- Unity
categories: Unity
---

# 注册事件

<!--more-->
## 新建脚本（EventHandle）
- 根据需求在EventHandle脚本中创建所需事件类型
例如
 ```c#
   public static event Action<int> ChuanDiShuZhi;
   public static void CallChuanDiShuZhi(int index)
      {
          ChaunDiShuZhi?.Invoke(index);
      }
 ```

## 在所需呼叫的脚本中进行注册并实现事件方法
例如（Player）

```c#
int id; //作为示例使用
private void OnEnable()
{
    EventHandle.ChuanDiShuZhi +=OnChuanDiShuZhi;
}
private void OnDisable()
{
     EventHandle.ChuanDiShuZhi -=OnChuanDiShuZhi;
}

public void OnChuanDiShuZhi(int index)
{
    index = id;
    //具体实现的操作代码
    DeBug.Log($"我是被注册的事件方法，我的编号是：{index}");
}
//下面示例在Awake中进行呼叫
public void Awake()
{
    EventHandle.CallChuanDiShuZhi(id);
}
```
[^_^]: 现在可以试试查看DeBug了
