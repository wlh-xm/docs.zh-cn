---
title: 参数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: c8bdb54e52b4c0d189f3bff72bdb24785c1a9c27
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="parameters-entity-sql"></a>参数 (Entity SQL)
参数是在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 之外（通常通过由主机语言使用的绑定 API）定义的变量。 每个参数都具有名称和类型。 参数名称在查询表达式中定义，并以 (@) 符号作为前缀。 这可以将它们与属性的名称或在查询中定义的其他名称区分开来。  
  
 主机语言绑定 API 提供用于绑定参数的 API。  
  
## <a name="example"></a>示例  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
