---
title: Filtrar para establecer posiciones de tabulación en texto dibujado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 76431d34504b40a299200693735a0a989127d683
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832312"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Filtrar para establecer posiciones de tabulación en texto dibujado
Puede establecer posiciones de tabulación para el texto mediante una llamada a la <xref:System.Drawing.StringFormat.SetTabStops%2A> método de un <xref:System.Drawing.StringFormat> objeto y, a continuación, pasando que <xref:System.Drawing.StringFormat> de objeto para el <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> hace que no admiten la incorporación de posiciones de tabulación en texto dibujado, aunque puede expandir la pestaña existente dejará de utilizar el <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> marca.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente establece las posiciones de tabulación en 150, 250 y 350. A continuación, el código muestra una lista de nombres y las puntuaciones de pruebas con pestañas.  
  
 La siguiente ilustración muestra el texto con pestañas:  
  
 ![Captura de pantalla que muestra una lista de nombres y las puntuaciones con pestañas.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 El código siguiente pasa dos argumentos de la <xref:System.Drawing.StringFormat.SetTabStops%2A> método. El segundo argumento es una matriz que contiene los desplazamientos de ficha. El primer argumento pasado a <xref:System.Drawing.StringFormat.SetTabStops%2A> es 0, lo que indica que el primer desplazamiento de la matriz se mide desde la posición 0, el borde izquierdo del rectángulo delimitador.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Utilizar fuentes y texto](using-fonts-and-text.md)
- [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)
