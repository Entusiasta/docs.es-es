---
title: 'Procedimiento Escribir un constructor Copy: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 169bdfc53d0c30ffc14e5a9525920679a94fbf23
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982146"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Procedimiento Escribir un constructor Copy (Guía de programación de C#)
C# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `Person`[class](../../../csharp/language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`. Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`. El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ICloneable>
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)
