---
title: StrongNameSignatureVerificationEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3f9dbbdf7ff560f292fed327a2ca1dd26c29a19
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491898"
---
# <a name="strongnamesignatureverificationex-function"></a>StrongNameSignatureVerificationEx (Función)
Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 [in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.  
  
 `fForceVerification`  
 [in] `true` para realizar la comprobación, incluso si es necesario reemplazar la configuración del registro; en caso contrario, `false`.  
  
 `pfWasVerified`  
 [out] `true` si la firma de nombre seguro se ha comprobado; en caso contrario, `false`. `pfWasVerified` También se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Si la comprobación se realizó correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 `StrongNameSignatureVerificationEx` Proporciona una funcionalidad similar a la [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) función. Sin embargo, el segundo parámetro de entrada y el parámetro de salida para `StrongNameSignatureVerificationEx` son del tipo `BOOLEAN` en lugar de `DWORD`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [StrongNameSignatureVerificationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [StrongNameSignatureVerification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
