---
title: IDebugDocumentContext2::GetDocument | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::GetDocument
helpviewer_keywords:
- IDebugDocumentContext2::GetDocument
ms.assetid: c6d46c5d-ade8-4dc8-9862-8fc7876658c4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2ce07bd2274bc2a4881acd98fb73266fc90c7bd8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341280"
---
# <a name="idebugdocumentcontext2getdocument"></a>IDebugDocumentContext2::GetDocument
Získá dokument, který obsahuje tento kontext dokumentu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDocument( 
   IDebugDocument2** ppDocument
);
```

```csharp
int GetDocument( 
   out IDebugDocument2 ppDocument
);
```

## <a name="parameters"></a>Parametry
`ppDocument`\
[out] Vrátí [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) objekt, který reprezentuje dokument, který obsahuje tento kontext dokumentu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je pro tyto moduly ladění, které poskytují dokumentů přímo do integrovaného vývojového prostředí. Jinak tato metoda by měla vrátit `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)