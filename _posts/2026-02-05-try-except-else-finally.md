# Python `try` / `except` / `else` / `finally` 学习笔记
Python中的 `try` / `except` / `else` / `finally`，之前没有很认真使用过。最近开发中用的比较多，也踩了一些坑。今天总结一下。

## 核心概念
- try 块：放可能抛异常的代码。
- except 块：捕获并处理特定异常。可以有多个 except 分支，按从上到下匹配。
- else 块（可选）：当 try 块没有抛出任何异常时执行。常用来把正常路径与异常路径分离。
- finally 块：无论是否发生异常、是否被 return、是否被取消，finally 块都会执行（除非进程被强制终止）。常用来释放资源或做清理工作。

## 基本结构
```
try:
    # 可能出错的代码
except SomeException as e:
    # 处理 SomeException
except (TypeError, ValueError):
    # 处理多个异常
except Exception:
    # 捕获其他常规异常（但不包括 BaseException 的子类，如 KeyboardInterrupt）
else:
    # 当没有异常发生时执行
finally:
    # 无论如何都会执行（清理工作）
```

**例子**：文件读写（使用 finally 做清理）
```
try:
    f = open("data.txt", "r")
    data = f.read()
    # 处理 data
except FileNotFoundError:
    print("文件不存在")
except OSError as e:
    print("IO 错误:", e)
else:
    print("读取成功，处理数据")
finally:
    # 确保文件一定被关闭
    try:
        f.close()
    except NameError:
        # f 可能未定义（打开失败）
        pass
```
不过文件读写更推荐的做法是使用 `with`（上下文管理器）：
```
try:
    with open("data.txt", "r") as f:
        data = f.read()
        # 处理 data
except FileNotFoundError:
    print("文件不存在")
```
### `except` 优先捕捉能处理的特定异常类型
```
try:
    ...
except FileNotFoundError:
    ...
except PermissionError:
    ...
except Exception as e:  # 更宽泛的捕获，但尽量避免滥用
    ...

```

### 抛出或者记录异常
```
try:
    ...
except ValueError:
    # 做点记录
    raise  # 把异常向上层继续传递
```

```
try:
    int("x")
except ValueError as e:
    raise RuntimeError("转换失败") from e
```


### **常见陷阱**：关于 `return` 与 `finally` 的交互  
`finally` 会在函数返回前执行。如果 `finally` 也有 `return`，会覆盖 `try/except` 中的返回值，导致难以发现的 bug，尽量避免在 finally 中返回值。 示例：
```
def f():
    try:
        return 1
    finally:
        print("finally runs")
        # 如果这里写 return 2，则函数最终返回 2（覆盖上面的 return 1）

print(f())  # 输出 finally runs 然后 1

```

### 最佳实践总结

- 优先捕获具体异常类型，不要用"裸" except。
- 使用 `else` 把正常逻辑与异常处理分开，增加可读性。
- 用 `finally` 或 `with` 处理资源清理；推荐使用 `with`（上下文管理器）替代显式 `finally` 关闭资源。
- 在 except 中记录异常堆栈（logging.exception），便于排查问题。
- 避免在 `finally` 中返回值或抛出新的异常，这会覆盖原始错误或返回值，导致难以调试。
- 若需要让异常继续向上层传播，使用 `raise`（或 `raise from` 以保留原异常链）。