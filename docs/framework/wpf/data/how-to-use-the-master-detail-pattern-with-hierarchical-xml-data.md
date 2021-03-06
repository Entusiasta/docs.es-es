---
title: Procedimiento Usar el patrón principal-detalle con datos XML jerárquicos
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 2b1ed34fe363f44a3a9eb80dc56d721868329717
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378111"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Filtrar Usar el patrón principal-detalle con datos XML jerárquicos
En este ejemplo se muestra cómo implementar el escenario principal-detalle con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo es el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] versión de datos del ejemplo se describe en [usar el patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md). En este ejemplo, los datos están en el archivo `League.xml`. Tenga en cuenta cómo la tercera <xref:System.Windows.Controls.ListBox> control realiza el seguimiento de cambios de selección en el segundo <xref:System.Windows.Controls.ListBox> mediante un enlace a su <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> propiedad.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.HierarchicalDataTemplate>
- [Temas "Cómo..."](data-binding-how-to-topics.md)
