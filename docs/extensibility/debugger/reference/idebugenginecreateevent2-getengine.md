---
title: IDebugEngineCreateEvent2::GetEngine | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineCreateEvent2::GetEngine
helpviewer_keywords:
- IDebugEngineCreateEvent2::GetEngine
ms.assetid: 187d24ed-9f9a-4418-a0ef-b8a19f54652c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: be6119f7542f47238f63e5b75453a46be2a32f5e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875336"
---
# <a name="idebugenginecreateevent2getengine"></a>IDebugEngineCreateEvent2::GetEngine
Načte objekt, který představuje nově vytvořený ladicího stroje (DE).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEngine( 
   IDebugEngine2** pEngine
);
```

```csharp
int GetEngine( 
   out IDebugEngine2 pEngine
);
```

#### <a name="parameters"></a>Parametry
 `pEngine`

 [out] Vrátí [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) objekt, který představuje nově vytvořený DE.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)