---
title: Procedimiento Dibujar una imagen usando un objeto ImageDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 9a9a7ee32104e44997e6eaada09edaac2b1d610e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355612"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>Filtrar Dibujar una imagen usando un objeto ImageDrawing
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.ImageDrawing> para dibujar una imagen. Un <xref:System.Windows.Media.ImageDrawing> permite mostrar un <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>. Para dibujar una imagen, se crea un <xref:System.Windows.Media.ImageDrawing> y establezca su <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> y <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> propiedades. El <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> propiedad especifica la imagen para dibujar y la <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> propiedad especifica la posición y tamaño de cada imagen.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un dibujo compuesto mediante cuatro <xref:System.Windows.Media.ImageDrawing> objetos. Este ejemplo genera la siguiente imagen:  
  
 ![Varios objetos DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")  
Cuatro objetos de un objeto ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Para obtener un ejemplo que muestra una manera sencilla de mostrar una imagen sin utilizar <xref:System.Windows.Media.ImageDrawing>, consulte [usar el elemento de imagen](../controls/how-to-use-the-image-element.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md)
- [PresentationOptions:Freeze (Atributo)](../advanced/presentationoptions-freeze-attribute.md)
