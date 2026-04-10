---
title: "C++ 智能指针实践：从 unique_ptr 到 shared_ptr"
date: 2026-04-10 14:00:00 +0800
categories: [技术, C++]
tags: [c++, smart-pointer, memory-management]
---

在现代 C++ 开发中，智能指针几乎取代了裸指针的日常使用。这篇文章分享我在实际项目中使用智能指针的一些经验。

## unique_ptr：默认首选

`std::unique_ptr` 是独占所有权的智能指针，开销几乎为零，应该作为默认选择。

```cpp
auto widget = std::make_unique<Widget>("editor");
widget->show();
// 离开作用域自动释放
```

**使用场景**：工厂函数返回值、类内资源管理、容器内存储多态对象。

## shared_ptr：按需共享

当多个对象需要共享同一资源时，使用 `std::shared_ptr`。但要注意引用计数的开销。

```cpp
auto config = std::make_shared<AppConfig>();
window->setConfig(config);
toolbar->setConfig(config);
```

> 避免循环引用，必要时搭配 `std::weak_ptr`。
{: .prompt-warning }

## 实际项目中的选择

在我的 Qt 编辑器项目中，采用的策略是：

1. **文档对象**：`unique_ptr`，编辑器独占
2. **配置对象**：`shared_ptr`，多个组件共享
3. **缓存项**：`weak_ptr`，允许被回收

```cpp
class Editor {
    std::unique_ptr<Document> doc_;
    std::shared_ptr<EditorConfig> config_;
    std::vector<std::weak_ptr<CacheEntry>> cache_;
};
```

## 小结

| 类型 | 所有权 | 开销 | 适用场景 |
|------|--------|------|----------|
| `unique_ptr` | 独占 | 近零 | 大多数情况 |
| `shared_ptr` | 共享 | 引用计数 | 多处持有 |
| `weak_ptr` | 观察 | 近零 | 缓存、防循环 |

选择智能指针的原则：**能用 unique 就不用 shared，能用 shared 就不用裸指针**。
