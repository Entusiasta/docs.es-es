---
title: Procedimiento Agregar y quitar nodos con el Control TreeView de Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: aca660c7b3269715e6551011261f9b84ba173db6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710360"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Filtrar Agregar y quitar nodos con el Control TreeView de Windows Forms mediante el diseñador
Dado que los Windows Forms <xref:System.Windows.Forms.TreeView> control muestra los nodos de forma jerárquica, al agregar un nodo que debe prestar atención a lo que es su nodo primario.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.TreeView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>Para agregar o quitar nodos en el diseñador  
  
1.  Seleccione el control <xref:System.Windows.Forms.TreeView>.  
  
2.  En el **propiedades** ventana, haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) situado junto a el <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad.  
  
     El **Editor TreeNode** aparece.  
  
3.  Para agregar nodos, debe existir un nodo raíz; Si no existe, primero debe agregar una raíz, haga clic en el **Agregar raíz** botón. A continuación, puede agregar nodos secundarios, seleccione la raíz o cualquier otro nodo y haga clic en el **agregar secundario** botón.  
  
4.  Para eliminar los nodos, seleccione el nodo para eliminar y, a continuación, haga clic en el **eliminar** botón.  
  
## <a name="see-also"></a>Vea también
- [TreeView (control)](treeview-control-windows-forms.md)
- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Cómo: Establecer iconos para el Control TreeView de formularios Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Cómo: Recorrer en iteración todos los nodos de un Control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
