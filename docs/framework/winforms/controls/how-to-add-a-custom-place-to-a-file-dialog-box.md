---
title: Cómo Agregar un lugar común a un cuadro de diálogo de archivos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: d9c1373a16f7d62c2933e01e513478fc6c9866d2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721884"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Cómo Agregar un lugar común a un cuadro de diálogo de archivos
Los cuadros de diálogo para abrir y guardar predeterminados en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] tienen un área en el lado izquierdo titulada **Vínculos favoritos**. Esta área se denomina ubicaciones personalizadas. El <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases le permiten agregar carpetas a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección.  
  
> [!NOTE]
>  En el orden de una ubicación personalizada aparezca en el <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad debe establecerse en `true` (valor predeterminado).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Para agregar una ubicación personalizada a un cuadro de diálogo de archivos  
  
-   Agregar una ruta de acceso, un GUID de carpetas conocidas, o un <xref:System.Windows.Forms.FileDialogCustomPlace> de objeto para el <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección del cuadro de diálogo.  
  
     En el siguiente ejemplo de código se muestra cómo agregar una ruta de acceso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [GUID de carpeta conocidos para lugares comunes de cuadros de diálogo de archivos](known-folder-guids-for-file-dialog-custom-places.md)
