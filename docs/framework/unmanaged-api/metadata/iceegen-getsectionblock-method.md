---
title: ICeeGen::GetSectionBlock (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e264a63dcea9c351289d1f63e1907f7c68779011
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496760"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock (Método)
Obtiene un bloque de sección del código base.  
  
 Este método está obsoleto y no debe usarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `section`  
 [in] La sección desde el que se va a recuperar un bloque de la base de código.  
  
 `len`  
 [in] La longitud del bloque que se va a recuperar.  
  
 `align`  
 [in] El byte, con respecto al principio de la sección con la que se va a alinear el primer byte del bloque. Esta es la posición del bloque dentro de la sección.  
  
 `ppBytes`  
 [out] Un puntero a una ubicación que recibe la dirección del bloque recuperado.  
  
## <a name="remarks"></a>Comentarios  
 Llamar a `GetSectionBlock` sólo si tiene requisitos de sección especial que no se controlan mediante otros métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
