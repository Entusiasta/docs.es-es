---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819247"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>No se admite la inferencia de tipos que acepten valores NULL en este contexto
Tipos de valor y las estructuras se pueden declarar que aceptan valores NULL.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sin embargo, no se puede utilizar la declaración que acepta valores NULL en combinación con la inferencia de tipos. Los ejemplos siguientes producen este error.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Identificador de error:** BC36629  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Use un `As` cláusula para declarar la variable que acepta valores NULL.  
  
## <a name="see-also"></a>Vea también

- [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
