---
title: IDebugDocumentContext2::Seek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f001eb73e3c24ac1c9f15a4bd2c37c8d2cbe660e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709522"
---
# <a name="idebugdocumentcontext2seek"></a>IDebugDocumentContext2::Seek
Přesune kontext dokumentu stanovený počet příkazů nebo řádky.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Seek( 
   int                      nCount,
   IDebugDocumentContext2** ppDocContext
);
```

```cpp
int Seek( 
   int                        nCount,
   out IDebugDocumentContext2 ppDocContext
);
```

#### <a name="parameters"></a>Parametry
 `nCount`

 [in] Počet příkazů nebo řádky pro přesun vpřed, v závislosti na kontextu dokumentu.

 `ppDocContext`

 [out] Vrátí nový [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objektu s novou pozici.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)