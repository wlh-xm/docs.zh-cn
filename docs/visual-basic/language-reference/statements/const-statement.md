---
title: Const 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: a5842e284eaa858e7a66160060123edc21858a3a
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="const-statement-visual-basic"></a>Const 语句 (Visual Basic)
用于声明和定义一个或多个常量。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>部件  
 `attributelist`  
 可选。 在此语句中声明的适用于所有常量的属性列表。 请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)中命令的尖括号 ("`<`"和"`>`")。  
  
 `accessmodifier`  
 可选。 用于指定哪些代码可以访问这些常量。 可以是[公共](../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../visual-basic/language-reference/modifiers/friend.md)， [Protected Friend](../modifiers/protected-friend.md)，[私有](../../../visual-basic/language-reference/modifiers/private.md)，或[私有受保护](../../language-reference/modifiers/private-protected.md)。
  
 `Shadows`  
 可选。 用于重新声明并隐藏基类中的编程元素。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。  
  
 `constantlist`  
 必须的。 正在此语句中声明的常量的列表。  
  
 `constant` `[ ,` `constant` `... ]`  
  
 每个 `constant` 都具有以下语法和部件：  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|部件|描述|  
|----------|-----------------|  
|`constantname`|必须的。 常数的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`datatype`|如果存在`Option Strict`是`On`。 数据类型的常数。|  
|`initializer`|必须的。 在编译时计算并将其分配给常量的表达式。|  
  
## <a name="remarks"></a>备注  
 如果应用程序中有一个值，永远不会更改，你可以定义一个命名的常量并用它来代替文字值。 名称是易于记住比值。 你可以只需一次定义常量，并在代码中的许多地方使用它。 如果需要更高版本中重新定义的值，`Const`语句是你需要进行更改的唯一位置。  
  
 你可以使用`Const`只能在模块或过程的级别。 这意味着*声明上下文*变量必须为类、 结构、 模块、 过程或块，并且不能是源文件、 命名空间或接口。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 局部常量 （在过程） 默认为公共访问，并且你不能在其上使用任何访问修饰符。 类和模块成员 （任何过程） 之外的常量默认为私有访问，并使用结构成员常量默认的公共访问权限。 你可以调整其访问级别有访问修饰符。  
  
## <a name="rules"></a>规则  
  
-   **声明上下文。** 常量是在模块级别，在任何过程中，外部声明*成员常量*; 它是类、 结构的成员或模块，其用于声明它。  
  
     在过程级别声明的常量是*局部常量*; 它是本地过程或声明它的块。  
  
-   **属性。** 可以将特性应用于成员常数上，而不是局部常量。 属性提供信息对程序集的元数据，这并没有意义的临时存储，如局部常量。  
  
-   **修饰符。** 默认情况下，所有常量都是`Shared`， `Static`，和`ReadOnly`。 声明常量时，不能使用任何这些关键字。  
  
     在过程级别，不能使用`Shadows`或任何访问修饰符来声明局部常量。  
  
-   **多个常量。** 你可以声明多个常量在相同的声明语句中，指定`constantname`为每个部分。 用逗号分隔多个常量。  
  
## <a name="data-type-rules"></a>数据类型规则  
  
-   **数据类型。** `Const`语句可以声明一个变量的数据类型。 你可以指定任何数据类型或枚举的名称。  
  
-   **默认类型。** 如果不指定`datatype`，常量将采用的数据类型`initializer`。 如果同时指定了`datatype`和`initializer`的数据类型`initializer`必须可转换为`datatype`。 如果既没有`datatype`也不`initializer`存在，则数据类型默认为`Object`。  
  
-   **不同类型。** 你可以通过使用单独指定不同的常数的不同数据类型`As`子句为每个声明的变量。 但是，不能声明多个常量使用一组公共将相同类型的`As`子句。  
  
-   **初始化。** 必须初始化值的中的每个常量`constantlist`。 你使用`initializer`来提供要分配给常量的表达式。 表达式可以是文本、 已定义，其他常量和枚举成员已定义的任意组合。 可以使用算术和逻辑运算符来组合这些元素。  
  
     不能使用变量或函数中的`initializer`。 但是，可以使用转换关键字如`CByte`和`CShort`。 你还可以使用`AscW`如果调用与一个常量`String`或`Char`自变量，因为可以在编译时计算的。  
  
## <a name="behavior"></a>行为  
  
-   **作用域。** 局部常量是仅从其过程或块中访问。 成员常量是可从其类、 结构或模块内任意位置访问。  
  
-   **限定。** 代码类之外，结构或模块必须使用限定成员常量的名称替换该类、 结构或模块的名称。 过程或块不能引用该过程或块中任何局部常量之外的代码。  
  
## <a name="example"></a>示例  
 下面的示例使用`Const`语句可以声明用于代替文字值的常量。  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>示例  
 如果数据类型定义常量`Object`，Visual Basic 编译器提供给它的一种`initializer`，而不是`Object`。 在下面的示例中，常量`naturalLogBase`具有运行时类型`Decimal`。  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 上面的示例使用<xref:System.Type.ToString%2A>方法<xref:System.Type>返回对象[GetType 运算符](../../../visual-basic/language-reference/operators/gettype-operator.md)，这是因为<xref:System.Type>不能转换为`String`使用`CStr`。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [常量和枚举](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [常量和枚举](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
