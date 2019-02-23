---
title: IDebugActivateDocumentEvent2::GetDocument | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugActivateDocumentEvent2::GetDocument
helpviewer_keywords:
- GetDocument method
- IDebugActivateDocumentEvent2::GetDocument method
ms.assetid: b3c32f1b-f3de-409d-920d-ba7b3fa84fcd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2c16a7a390da2e571ad0cc83041106b257048054
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56701729"
---
# <a name="idebugactivatedocumentevent2getdocument"></a>IDebugActivateDocumentEvent2::GetDocument
Získá dokument k aktivaci.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDocument ( 
   IDebugDocument2** ppDoc
);
```

```csharp
int GetDocument ( 
   out IDebugDocument2 ppDoc
);
```

#### <a name="parameters"></a>Parametry
 `ppDoc`

 [out] Vrátí [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) objekt, který reprezentuje dokumentu, který má být aktivován.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)