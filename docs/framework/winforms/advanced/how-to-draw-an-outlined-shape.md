---
title: Filtrar Dibujar una forma con contorno
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 598706b381d12b8e820747ca872146bdb5e300c7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722638"
---
# <a name="how-to-draw-an-outlined-shape"></a>Filtrar Dibujar una forma con contorno
En este ejemplo se dibuja elipses con contorno y rectángulos en un formulario.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos. No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño u ocultado por otro formulario. Para que el contenido automáticamente volver a dibujar, se debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
## <a name="robust-programming"></a>Programación sólida  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como <xref:System.Drawing.Pen> y <xref:System.Drawing.Graphics> objetos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
