---
title: + （字符串串联）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 1826d1267f0ee5ad8320cf1d1ab36f87adf765a5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="-string-concatenation-entity-sql"></a>+（字符串串联）(Entity SQL)
串联两个字符串。  
  
## <a name="syntax"></a>语法  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 EDM.String 数据类型的任何有效表达式。 这两个表达式都必须具有相同的数据类型，或者一个表达式必须能够隐式转换为另一表达式的数据类型。  
  
## <a name="result-types"></a>结果类型  
 对这两个参数进行隐式类型提升而产生的数据类型。 有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 + 运算符以串联两个字符串。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。  
  
2.  将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [概念模型类型 (CSDL)](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
