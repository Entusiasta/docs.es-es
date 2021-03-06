---
title: Filtrar Usar un objeto ThicknessConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 7dcac523ad105f074df11cdd74126536a60497b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57350706"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Filtrar Usar un objeto ThicknessConverter
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarlo para cambiar el grosor del borde.  
  
 El ejemplo define un método personalizado llamado `changeThickness`; en primer lugar, este método convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Windows.Thickness>y posteriormente convierte el contenido en un <xref:System.String>. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.Thickness>. Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de la <xref:System.Windows.Controls.Border>.  
  
 En este ejemplo no se ejecuta.  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [Cómo: Cambiar la propiedad Margin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))
- [Cómo: Convertir un elemento ListBoxItem en un nuevo tipo de datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))
- [Información general sobre elementos Panel](../controls/panels-overview.md)
