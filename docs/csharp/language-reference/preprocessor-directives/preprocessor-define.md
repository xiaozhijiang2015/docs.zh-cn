---
title: "#define（C# 参考）| Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 0db5a86fee1ed2139ae5046ada66121ffe8210b1
ms.contentlocale: zh-cn
ms.lasthandoff: 05/10/2017

---
# <a name="define-c-reference"></a>#define（C# 参考）
使用 `#define` 来定义符号。 将符号用作传递给 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令的表达式时，该表达式的计算结果为 `true`，如以下示例所示：  
  
 `#`  `define`   `DEBUG`  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  `#define` 指令不能用于声明常量值，这与 C 和 C++ 中的通常做法一样。 C# 中的常量最好定义为类或结构的静态成员。 如果具有多个此类常量，请考虑创建一个单独的“常量”类来容纳它们。  
  
 符号可用于指定编译的条件。 可通过 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或 [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 测试符号。 还可以使用 `conditional` 属性来执行条件编译。  
  
 可以定义一个符号，但不能向符号分配值。 文件中必须先出现 `#define` 指令，才能使用并非同时也是预处理器指令的任何指示。  
  
 还可以通过 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 编译器选项来定义符号。 可以通过 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 取消定义符号。  
  
 使用 `/define` 或 `#define` 定义的符号与具有相同名称的变量不冲突。 也就是说，变量名称不应传递给预处理器指令，且符号仅能由预处理器指令评估。  
  
 使用 `#define` 创建的符号的作用域是在其中定义该符号的文件。  
  
 如以下示例所示，必须将 `#define` 指令放在文件顶部。  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 有关如何取消对符号进行定义的示例，请参阅 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)。  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)   
 [C# 编程指南](../../../csharp/programming-guide/index.md)   
 [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [如何：使用跟踪和调试进行条件编译](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)   
 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)   
 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
