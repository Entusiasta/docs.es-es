---
title: FunctionEnter3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9e94c1904d8675af59e6ed5b49c2229e1214e8b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469227"
---
# <a name="functionenter3withinfo-function"></a>FunctionEnter3WithInfo (Función)
Notifica al generador de perfiles que se pasa a una función de control y proporciona un identificador que puede pasarse a la [método ICorProfilerInfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar los argumentos de marco y la función de la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionIDOrClientID`  
 [in] El identificador de la función a la que se pasa el control.  
  
 `eltInfo`  
 [in] Controlador opaco que representa información sobre un marco de pila determinado. Este identificador es válido solo durante la devolución de llamada a la que se pasa.  
  
## <a name="remarks"></a>Comentarios  
 El `FunctionEnter3WithInfo` método de devolución de llamada notifica el generador de perfiles cuando se llama a las funciones y permite usar el generador de perfiles la [método ICorProfilerInfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) para inspeccionar los valores de argumento. Para obtener acceso a información del argumento, el `COR_PRF_ENABLE_FUNCTION_ARGS` marca se ha establecido. El generador de perfiles puede utilizar el [SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, utilice el [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar su implementación de esta función.  
  
 El `FunctionEnter3WithInfo` función es una devolución de llamada; debe implementar. La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.  
  
 La implementación de `FunctionEnter3WithInfo` no debe bloquearse, porque ello retrasará la recolección de elementos. La implementación no debe intentar una recolección de elementos, ya que la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionEnter3WithInfo` devuelve.  
  
 El `FunctionEnter3WithInfo` función no debe llamar al código administrado o provocar una asignación de memoria administrada de ninguna manera.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)
- [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
