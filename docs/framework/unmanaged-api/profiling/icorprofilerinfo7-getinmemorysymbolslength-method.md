---
title: 'Icorprofilerinfo7:: Getinmemorysymbolslength (método)'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550acc8d696cbd9e82d05e09c48a8c929af23673
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487487"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>Icorprofilerinfo7:: Getinmemorysymbolslength (método)
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Devuelve la longitud de una secuencia de símbolos en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo que contiene la secuencia en memoria.  
  
 pCountSymbolBytes  
 [out] Un puntero a un `DWORD` valor que, cuando el método vuelve, contiene la longitud de la secuencia en bytes.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve `S_OK` si puede determinarse la longitud de la secuencia de memoria, incluso si es cero (0).  
  
 El método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` si el método se creó mediante <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Comentarios  
 Si el módulo tiene los símbolos en memoria, la longitud de la secuencia se coloca en `pCountSymbolBytes`. Si el módulo no tiene símbolos en memoria, `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  La implementación actual no admite Reflection.Emit. Si se creó el módulo mediante Reflection.Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
