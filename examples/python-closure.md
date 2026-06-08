# Action Card: Python 闭包 (Closures)

## 1. Real Need
理解闭包的工作机制、常见陷阱，以及在实际代码中何时用闭包替代类。

## 2. Expert Resources

### Python 官方文档 — Nested Scopes
- **Why experts check it:** 定义了 LEGB 规则和 free variable 的精确语义
- **What to do:** 搜索 `python reference expressions.html#resolution-of-names`，重点读 "closure" 和 "free variable" 定义
- **What to extract:** cell object 的生命周期、`nonlocal` 的作用范围
- **Common beginner miss:** 只看教程博客，不知道 `__closure__` 属性的存在

### `inspect` 模块 + `__closure__` 属性
- **Why experts check it:** 直接证明闭包"捕获"了什么变量，调试时最可靠
- **What to do:** `f.__closure__[0].cell_contents` 查看捕获值
- **What to extract:** 变量是按 cell（引用）捕获，不是按值复制
- **Common beginner miss:** 以为闭包在函数定义时就"快照"了值

### 循环+闭包 Late Binding 案例
- **Why experts check it:** 这是闭包最常见的 production bug 来源
- **What to do:** 亲手写出错版本，再用两种方式修复
- **What to extract:** 闭包捕获的是变量名（cell），不是当时的值

---

## 3. Correct Path

```
理解 LEGB 规则
→ 写一个最小闭包（counter）
→ 用 __closure__ 证明捕获的是 cell
→ 复现 loop late-binding bug
→ 用 default argument 修复
→ 用 nonlocal 修改外层变量
→ 判断：闭包 vs 类，哪种更清晰
```

---

## 4. Avoid

- 只读博客定义，不动手写出 bug 并修复
- 混淆 `global` 和 `nonlocal`（`global` 指模块级，`nonlocal` 指最近外层函数）
- 用闭包存大量状态（应改用类）

---

## 5. Gateway Minimal Action

**目标：** 证明闭包按 cell 引用捕获，而非按值快照，并能修复 loop 陷阱。

**步骤：**

```python
# 1. 最小闭包 + cell 验证
def make_counter(start=0):
    count = start
    def increment():
        nonlocal count
        count += 1
        return count
    return increment

c = make_counter()
print(c(), c(), c())              # 1 2 3
print(c.__closure__[0].cell_contents)  # 3  ← 捕获的是 cell，不是快照

# 2. 复现 late-binding bug
funcs_bad = [lambda: i for i in range(3)]
print([f() for f in funcs_bad])   # [2, 2, 2]  ← 全是2，bug!

# 3. 修复：default argument 强制快照
funcs_good = [lambda i=i: i for i in range(3)]
print([f() for f in funcs_good])  # [0, 1, 2]  ← 正确
```

**Evidence（成功标志）：**
- `c.__closure__[0].cell_contents` 返回 `3`（证明是 cell 引用）
- `funcs_bad` 输出 `[2, 2, 2]`（亲眼看到 bug）
- `funcs_good` 输出 `[0, 1, 2]`（修复验证）

---

## 6. Save This

```markdown
## Python 闭包速查

### 核心机制
- 闭包捕获的是 **cell（变量引用）**，不是定义时的值快照
- 用 `f.__closure__[0].cell_contents` 查看捕获内容

### nonlocal vs global
- `nonlocal x` → 修改最近外层函数的 x
- `global x`   → 修改模块级 x

### Loop Late-Binding 陷阱
```python
# 错误：全输出最后一个值
[lambda: i for i in range(3)]

# 修复：default argument 强制捕获当前值
[lambda i=i: i for i in range(3)]
```

### 闭包 vs 类
- 状态简单、方法单一 → 用闭包
- 状态复杂、多个方法 → 用类
```

---

## 7. Optional Retro Hooks

运行完 gateway action 后回答：
- `__closure__` 输出了什么？和你预期一样吗？
- `funcs_bad` 的 bug 你能用一句话解释给别人听吗？
- 你见过哪些生产代码用闭包替代类？合理吗？
- `nonlocal` 的限制是什么（能跨两层吗）？