---
title: ISymUnmanagedWriter::SetScopeRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3657ef40fce3d9d29e0cf6c27e8eb527be0f150e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489025"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>ISymUnmanagedWriter::SetScopeRange (Método)
Define el intervalo de desplazamiento del ámbito léxico especificado. El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos. Los ámbitos deben formar una jerarquía. Elementos del mismo nivel no se pueden superponer.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a>Parámetros  
 `scopeId`  
 [in] El identificador de ámbito para el ámbito.  
  
 `startOffset`  
 [in] El desplazamiento, en bytes, de la primera instrucción del ámbito léxico desde el principio del método.  
  
 `endOffset`  
 [in] El desplazamiento, en bytes, de la última instrucción del ámbito léxico desde el principio del método.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Comentarios  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con `ISymUnmanagedWriter::SetScopeRange` definir un ámbito de desplazamiento inicial y final en un momento posterior. En este caso, los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) se omiten. Los identificadores de ámbito solo son válidos en el método actual.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
