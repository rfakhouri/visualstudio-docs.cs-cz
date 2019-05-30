---
title: IDebugDocumentContext2::Seek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 413b1416adcd4b20231666e25f6a8044e632198b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325433"
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

## <a name="parameters"></a>Parametry
`nCount`\
[in] Počet příkazů nebo řádky pro přesun vpřed, v závislosti na kontextu dokumentu.

`ppDocContext`\
[out] Vrátí nový [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objektu s novou pozici.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)