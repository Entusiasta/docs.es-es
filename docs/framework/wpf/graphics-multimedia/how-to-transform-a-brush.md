---
title: Filtrar Transformar un pincel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 990c82b4844ce3ca7f5b553b180280b6b37496ca
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373769"
---
# <a name="how-to-transform-a-brush"></a>Procedimiento Transformar un pincel
En este ejemplo se muestra cómo transformar <xref:System.Windows.Media.Brush> objetos mediante el uso de sus dos propiedades de transformación: <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Los ejemplos siguientes usan una <xref:System.Windows.Media.RotateTransform> para girar el contenido de un <xref:System.Windows.Media.ImageBrush> 45 grados.  
  
 La siguiente ilustración muestra el <xref:System.Windows.Media.ImageBrush> sin un <xref:System.Windows.Media.RotateTransform>, con el <xref:System.Windows.Media.RotateTransform> aplicado a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad y con el <xref:System.Windows.Media.RotateTransform> aplicado a la <xref:System.Windows.Media.Brush.Transform%2A> propiedad.  
  
 ![Valores de Brush RelativeTransform y Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Ejemplo  
 El primer ejemplo se aplica un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad de un <xref:System.Windows.Media.ImageBrush>. El <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> las propiedades de un <xref:System.Windows.Media.RotateTransform> objeto se establecen en 0,5, que es la coordenada relativa del punto central de este contenido. Como resultado, el <xref:System.Windows.Media.ImageBrush> contenido gira sobre su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 El segundo ejemplo también se aplica un <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Media.ImageBrush>; sin embargo, este ejemplo se usa el <xref:System.Windows.Media.Brush.Transform%2A> propiedad en lugar de la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad.  
  
 Para girar el pincel sobre su centro, el ejemplo establece la <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades de la <xref:System.Windows.Media.RotateTransform> objeto en coordenadas absolutas. Como el pincel pinta un rectángulo de 175 x 90 píxeles, el punto central del rectángulo es (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Para obtener una descripción de cómo el <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A> propiedades de trabajo, consulte el [información general sobre la transformación de pinceles](brush-transformation-overview.md).  
  
 Para ver el ejemplo completo, consulte [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Ejemplo de pinceles). Para más información sobre los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre la transformación de pinceles](brush-transformation-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
