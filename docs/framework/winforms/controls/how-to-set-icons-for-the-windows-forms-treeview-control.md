---
title: Filtrar Establecer iconos para el Control TreeView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 515ff2bd4ab0f4fa93eada61396bd45c587cded6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703574"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Filtrar Establecer iconos para el Control TreeView de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.TreeView> control puede mostrar iconos junto a cada nodo. Los iconos se sitúan inmediatamente a la izquierda del texto del nodo. Para mostrar estos iconos, debe asociar la vista de árbol con un <xref:System.Windows.Forms.ImageList> control. Para obtener más información acerca de las listas de imágenes, consulte [componente ImageList](imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Un error en Microsoft .NET Framework versión 1.1 evita que las imágenes que aparecen en <xref:System.Windows.Forms.TreeView> nodos cuando la aplicación llama a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Para evitar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> en su `Main` método inmediatamente después de llamar a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Este error se ha corregido en [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Para mostrar imágenes en una vista de árbol  
  
1.  Establecer el <xref:System.Windows.Forms.TreeView> del control <xref:System.Windows.Forms.TreeView.ImageList%2A> propiedad existente <xref:System.Windows.Forms.ImageList> control que desea usar.  
  
     Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en el código.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Establecer el nodo <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> y <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> propiedades. El <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> propiedad determina la imagen mostrada para los Estados del nodo normal y expandido y el <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> propiedad determina la imagen mostrada para el estado del nodo seleccionado.  
  
     Estas propiedades pueden establecerse en el código o dentro del Editor TreeNode. Para abrir el Editor TreeNode, haga clic en el botón de puntos suspensivos ( ![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad en la ventana Propiedades.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>Vea también
- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar nodos con el Control TreeView de formularios Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Cómo: Recorrer en iteración todos los nodos de un Control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
