---
title: Filtrar Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d0b25f56caf3f25b6e649c05ecf1cbe50046dd93
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362375"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Procedimiento Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio
En este ejemplo se muestra cómo controlar un <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse. Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y propiedades que se animan y, a continuación, inicia el guión gráfico. Si da <xref:System.Windows.Media.Animation.BeginStoryboard> especificando un nombre de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, facilitar un guión gráfico controlable. A continuación, puede controlar interactivamente el guión gráfico después de iniciarse.  
  
 Utilice las siguientes acciones de guión gráfico junto con <xref:System.Windows.EventTrigger> objetos que se va a controlar un guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Reanuda un guión gráfico en pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Avanza un guión gráfico hasta el final de su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico, liberando los recursos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza acciones de guión gráfico controlable controlar interactivamente un guión gráfico.  
  
 **Nota:** Para ver un ejemplo de controlar un guión gráfico mediante código, consulte [controlar un guión gráfico después de que se inicia utilizando sus métodos interactivos](how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Para obtener ejemplos adicionales, vea el [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Controlar un guión gráfico una vez iniciado usando métodos interactivos](how-to-control-a-storyboard-after-it-starts.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
