---
title: ICorDebugEval::CallFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364156"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction (Método)

Configura una llamada a la función especificada.

Este método está obsoleto en .NET Framework versión 2.0. Use [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) en su lugar.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Parámetros

`pFunction`\
[in] Puntero a un objeto ICorDebugFunction que especifica la función debe llamarse.

`nArgs`\
[in] El número de argumentos de la función.

`ppArgs`\
[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que especifica un argumento que se pasará a la función.

## <a name="remarks"></a>Comentarios

Si la función es virtual, `CallFunction` llevará a cabo distribución virtual. Si la función está en un dominio de aplicación diferente, se producirá una transición siempre y cuando todos los argumentos son también en ese dominio de aplicación.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET framework:** 1.1, 1.0

## <a name="see-also"></a>Vea también

- [CallParameterizedFunction (método)](icordebugeval2-callparameterizedfunction-method.md)