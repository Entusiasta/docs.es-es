---
title: Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d024420fbbc3efbd3d19bb58c9379eacbafac5d3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820742"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior Para volver a habilitar la evaluación de funciones, vuelva a intentarlo o reinicie la depuración.  
  
 En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.  
  
 Las posibles causas de una llamada a procedimiento en tiempo de espera incluyen un bucle infinito o *bucle sin fin*. Para obtener más información, consulte [para... Instrucción Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Es un caso especial de un bucle infinito *recursividad*. Para obtener más información, consulte [procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Identificador de error:** BC30957  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si es posible, determine cuál era la evaluación de función anterior y lo que lo produjo que se superara el tiempo de espera. De lo contrario, podría encontrar de nuevo este error.  
  
2.  O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.  
  
## <a name="see-also"></a>Vea también

- [Depurar en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Desplazarse por el código con el depurador](/visualstudio/debugger/navigating-through-code-with-the-debugger)
