---
title: Captura del mouse (ratón) en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: afb58df99ea30f5e7e6ab5b9156af195d273c44d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712713"
---
# <a name="mouse-capture-in-windows-forms"></a>Captura del mouse (ratón) en formularios Windows Forms
*Captura el mouse* se refiere a un control dirige la entrada del mouse. Cuando un control ha capturado el mouse, recibe la entrada del mouse si el puntero está dentro de sus bordes.  
  
## <a name="setting-mouse-capture"></a>Configuración de captura del Mouse  
 En Windows Forms se captura el mouse por el control cuando el usuario presiona un botón del mouse en un control y se suelta el mouse por el control cuando el usuario suelta el botón del mouse.  
  
 El <xref:System.Windows.Forms.Control.Capture%2A> propiedad de la <xref:System.Windows.Forms.Control> clase especifica si un control ha capturado el mouse. Para determinar cuándo un control pierde la captura del mouse, controle el <xref:System.Windows.Forms.Control.MouseCaptureChanged> eventos.  
  
 Ventana de primer plano puede capturar el mouse. Cuando una ventana en segundo plano intenta capturar el mouse, la ventana recibe los mensajes solo para los eventos del mouse que se producen cuando el puntero del mouse está dentro de la parte visible de la ventana. Además, incluso si la ventana de primer plano ha capturado el mouse, el usuario puede hacer clic en otra ventana, llevándola a primer plano. Cuando se captura el mouse, teclas de método abreviado no funcionan.  
  
## <a name="see-also"></a>Vea también
- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
