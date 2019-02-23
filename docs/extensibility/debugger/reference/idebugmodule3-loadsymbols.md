---
title: IDebugModule3::LoadSymbols | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9068eed8881124e75f06f4b97d3430ff3ef80e8a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717023"
---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
Načte symboly pro aktuální modul.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT LoadSymbols(
   void
);
```

```csharp
int LoadSymbols();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud metoda uspěje, vrátí `S_OK`. Pokud selže, vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda načte symboly z aktuální cesta pro vyhledávání (které mohou být změněny voláním [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) metoda).

 Tato metoda je upřednostňované nad [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)
- [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)