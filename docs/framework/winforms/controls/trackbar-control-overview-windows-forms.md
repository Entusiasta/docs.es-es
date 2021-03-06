---
title: Información general del control TrackBar (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 74a8feba14b7e2186fb64729cb915e53132805d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707019"
---
# <a name="trackbar-control-overview-windows-forms"></a>Información general del control TrackBar (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.TrackBar> control (a veces también denominado control "slider") se utiliza para navegar por una gran cantidad de información o para ajustar visualmente un valor numérico. El <xref:System.Windows.Forms.TrackBar> control consta de dos partes: el control de posición, también conocido como control deslizante y las marcas de graduación. El control de posición es la parte que se puede ajustar. Su posición corresponde a la <xref:System.Windows.Forms.TrackBar.Value%2A> propiedad. Las marcas de graduación son indicadores visuales espaciados a intervalos regulares. Mueve la barra de seguimiento en incrementos que se especifique y se pueden alinear horizontal o verticalmente. Por ejemplo, puede usar la barra de seguimiento para controlar la intermitencia del cursor del mouse o velocidad de velocidad para un sistema.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades de clave de la <xref:System.Windows.Forms.TrackBar> control son <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, y <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> es el espaciado de las marcas de paso. <xref:System.Windows.Forms.TrackBar.Minimum%2A> y <xref:System.Windows.Forms.TrackBar.Maximum%2A> son los valores mínimo y máximo que se pueden representar en la barra de seguimiento.  
  
 Otras dos propiedades importantes son <xref:System.Windows.Forms.TrackBar.SmallChange%2A> y <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. El valor de la <xref:System.Windows.Forms.TrackBar.SmallChange%2A> propiedad es el número de posiciones que se desplaza el control de posición en respuesta a la presionar la tecla flecha izquierda o derecha. El valor de la <xref:System.Windows.Forms.TrackBar.LargeChange%2A> propiedad es el número de posiciones en el cuadro de desplazamiento se mueve en respuesta a la presionar la tecla RE PÁG o AV PÁG o en respuesta a mouse hace clic en la barra de seguimiento a ambos lados del control de posición.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.TrackBar>
- [TrackBar (control)](trackbar-control-windows-forms.md)
