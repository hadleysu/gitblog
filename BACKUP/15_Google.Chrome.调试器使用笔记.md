# [Google Chrome 调试器使用笔记](https://github.com/hadleysu/gitblog/issues/15)

# Google Chrome 调试器使用笔记

## 1. **调试器的基本概念**

- **调试器** (Debugger) 是开发者工具的一部分，用于逐行检查代码的执行过程。
- 通过调试，可以在 JavaScript 运行时暂停执行，查看变量的值、执行的路径以及逻辑错误。

## 2. **打开调试器**

- 使用快捷键 `F12` 或 `Ctrl + Shift + J`（Windows）打开开发者工具。
- 选择 **Sources** 面板，进入调试器界面。

## 3. **设置断点 (Breakpoints)**

- 断点用于告诉调试器在哪一行代码暂停执行。设置断点的方法如下：
  - 在 **Sources** 面板中找到要调试的 JavaScript 文件。
  - 点击行号，设置断点。调试器将在执行到该行时自动暂停，允许你检查当前的变量状态。

## 4.**使用 `debugger;` 语句**

在代码中插入 `debugger;` 语句可以强制浏览器在该行代码处暂停执行，使得你能够手动检查变量值、执行单步调试等。这个语句相当于在开发者工具中手动设置一个断点。

```javascript
function calculateSum(a, b) {
  debugger; // 在这里暂停代码执行
  return a + b;
}

calculateSum(5, 10);
```

在上面的例子中，当代码执行到 `debugger;` 语句时，Chrome 的开发者工具会自动暂停代码执行，你可以在“Sources”面板中查看并逐步调试代码。

## 5. **逐步执行代码**

- **Resume Script Execution (F8)**: 继续执行到下一个断点或到脚本结束。
- **Step Over (F10)**: 执行当前行，然后跳到下一行。
- **Step Into (F11)**: 进入当前行中调用的函数。
- **Step Out (Shift + F11)**: 从当前函数跳出，返回到调用它的代码行。

## 6. **检查变量和表达式**

- **Scope** 视图：可以查看当前作用域内的所有变量。
- **Watch** 视图：手动添加表达式，监视特定变量的值。
- **Call Stack** 视图：查看当前执行的函数调用链。

## 7. **常见的调试场景**

- **调试未定义的变量**：在遇到 `undefined` 错误时，通过调试器查看变量的赋值过程。
- **调试条件断点**：在特定条件下暂停执行，使用右键点击行号，选择 `Add conditional breakpoint`，并输入相应的条件表达式。

  - 定义：

    条件断点允许你在满足特定条件时暂停代码执行，而不是每次运行到断点时都暂停。这对于在大型循环或复杂逻辑中，只有特定情况下才需要调试时非常有用。

  - 示例：

    ```javascript
    for (let i = 0; i < 20; i++) {
      console.log("Current value of i:", i);
      // 只有当 i 大于 10 时，才会暂停执行
      // 在这里右键点击行号，选择 'Add conditional breakpoint'
    }
    ```

    假设你在 `console.log('Current value of i:', i);` 这一行设置了条件断点，并输入条件 `i > 10`，那么当 `i` 的值大于 10 时，调试器才会暂停代码执行。即当代码执行到该行且条件为真时，代码将暂停执行。

  - 应用场景：

    这种调试方式特别适合在循环或者多次重复执行的代码块中，你只关心某个特定条件下的行为。例如，当你调试一个数据处理循环时，只需要在数据满足某个条件时才查看详细信息，那么条件断点可以节省你大量时间。

## 8. **结合 Console 和 Debugger**

- 使用 `console.log` 或 `console.table`输出重要的变量值，同时结合断点，可以更精确地了解代码的执行流程。

## 9. **终止调试**

- 关闭开发者工具或移除所有断点，点击 **Resume script execution** 完成剩余代码的执行

## 10. **总结**

- 调试器的使用有助于提高代码质量，快速定位和修复错误。
- 定期使用调试工具进行代码检查，而不是依赖于猜测和重复的 `console.log`。

## 11. **参考文档**

- [Google Chrome Developer Tools Documentation](https://developer.chrome.com/docs/devtools/)
