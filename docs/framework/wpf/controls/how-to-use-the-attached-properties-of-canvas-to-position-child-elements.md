---
title: Filtrar Utilizar las propiedades asociadas de Canvas para situar elementos secundarios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: a34bac644bd0fa4c15d76d72d0502b311c49d018
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365339"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Filtrar Utilizar las propiedades asociadas de Canvas para situar elementos secundarios
En este ejemplo se muestra cómo usar las propiedades asociadas de <xref:System.Windows.Controls.Canvas> para situar elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente agrega cuatro <xref:System.Windows.Controls.Button> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.Canvas>. Cada elemento se representa mediante un <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, y <xref:System.Windows.Controls.Canvas.Top%2A>.
Cada <xref:System.Windows.Controls.Button> se sitúa en relación con el elemento primario <xref:System.Windows.Controls.Canvas> y según su valor de propiedad asignado.  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [Información general sobre elementos Panel](panels-overview.md)
- [Temas "Cómo..."](canvas-how-to-topics.md)
- [Información general sobre propiedades asociadas](../advanced/attached-properties-overview.md)
