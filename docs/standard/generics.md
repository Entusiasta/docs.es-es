---
title: Información general de tipos genéricos (genéricos)
description: Obtenga información sobre cómo los genéricos actúan como plantillas de código que le permiten definir estructuras de datos con seguridad de tipos sin confirmar un tipo de datos real.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 3c1181f5be717f328ae906c6009fc8a34b904c89
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465430"
---
# <a name="generic-types-overview"></a>Información general de tipos genéricos

Los desarrolladores utilizan genéricos en todo momento en .NET, ya sea implícita o explícitamente. Al usar LINQ en .NET, ¿alguna vez observó que estaba trabajando con <xref:System.Collections.Generic.IEnumerable%601>? O si alguna vez ha visto un ejemplo en línea de un "repositorio genérico" para comunicarse con bases de datos mediante Entity Framework, ¿observó que la mayoría de los métodos devuelven IQueryable\<T>? Probablemente se pregunte qué significa la **T** en estos ejemplos y por qué aparece.

Introducidos por primera vez en .NET Framework 2.0, los **genéricos** son esencialmente una "plantilla de código" que permite a los desarrolladores definir estructuras de datos [con seguridad de tipos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) sin confirmar un tipo de datos real. Por ejemplo, <xref:System.Collections.Generic.List%601> es una [colección genérica](xref:System.Collections.Generic) que se puede declarar y usar con cualquier tipo, como `List<int>`, `List<string>` o `List<Person>`.

Para entender por qué los genéricos son útiles, vamos a echar un vistazo a una clase específica antes y después de agregar genéricos: <xref:System.Collections.ArrayList>. En .NET Framework 1.0, los elementos `ArrayList` eran de tipo <xref:System.Object>. Esto significaba que cualquier elemento agregado se convertía desapercibidamente en un `Object`. Lo mismo podría suceder al leer los elementos de la lista. Este proceso se conoce como [conversión boxing y unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), y afecta al rendimiento. Sin embargo, más que eso, hay ninguna manera de determinar el tipo de datos en la lista en el tiempo de compilación. Por ello, algunos códigos son frágiles. Los genéricos solucionan este problema definiendo el tipo de datos que va a contener cada instancia de la lista. Por ejemplo, solo puede agregar enteros a `List<int>` y solo puede agregar personas a `List<Person>`.

Los genéricos también están disponibles en el tiempo de ejecución. Esto significa que el tiempo de ejecución conoce qué tipo de estructura de datos está usando y puede almacenarla en memoria de modo más eficaz.

El ejemplo siguiente es un pequeño programa que muestra la eficacia que supone conocer el tipo de estructura de datos en el tiempo de ejecución:

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

Este programa genera un resultado similar al siguiente:

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

Lo primero que verá aquí es que la ordenación de la lista genérica es significativamente más rápida que la de la lista no genérica. También puede observar que el tipo de la lista genérica es distinto ([System.Int32]), mientras que el tipo de la lista no genérica es generalizado. Dado que el tiempo de ejecución sabe que el genérico `List<int>` es de tipo `ArrayList`, puede almacenar los elementos de la lista en una matriz de enteros subyacente en memoria, mientras el no genérico <xref:System.Int32> tiene que convertir cada elemento de la lista en un objeto. Como se muestra en este ejemplo, las conversiones adicionales consumen tiempo y ralentizan la ordenación de la lista.

Otra ventaja adicional de que el tiempo de ejecución conozca el tipo de la clase genérica es una mejor experiencia de depuración. Cuando se depura un genérico en C#, sabe qué tipo de cada elemento se encuentra en la estructura de datos. Sin genéricos, no sabría qué tipo de cada elemento estaba presente.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#: genéricos](../../docs/csharp/programming-guide/generics/index.md)
