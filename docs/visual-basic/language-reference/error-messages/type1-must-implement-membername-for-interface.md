---
title: <type1>'<typename>'debe implementar'<membername>'para la interfaz'<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 485680a2984a29037b2836fcba13cf1aa1e2e699
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822757"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<tipo1 >'\<typename >' debe implementar '\<membername >' para la interfaz '\<interfacename >'
'\<typename >' debe implementar '\<membername >' para la interfaz '\<interfacename >'. Propiedad de implementación debe tener coincidentes 'ReadOnly' o 'WriteOnly' especificadores.  
  
 Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento, propiedad o evento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **Identificador de error:** BC30154  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declarar a un miembro con el mismo nombre y firma, tal como se define en la interfaz. No olvide incluir al menos el `End Function`, `End Sub`, o `End Property` instrucción.  
  
2.  Agregar un `Implements` cláusula al final de la `Function`, `Sub`, `Property`, o `Event` instrucción. Por ejemplo:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se usa en la misma forma que la definición de interfaz.  
  
4.  Al implementar una propiedad, declare `Get` y `Set` procedimientos, según corresponda.  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
