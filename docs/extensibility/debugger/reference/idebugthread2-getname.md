---
title: IDebugThread2::GetName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetName
helpviewer_keywords:
- IDebugThread2::GetName
ms.assetid: eec54b8f-4a0e-4919-b0f9-81d4bd1e0b6f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 04a76c88e5fd3eee146f6c174087298bac2b6974
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56679902"
---
# <a name="idebugthread2getname"></a>IDebugThread2::GetName
Získá název vlákna.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName ( 
   BSTR* pbstrName
);
```

```csharp
int GetName ( 
   out string pbstrName
);
```

#### <a name="parameters"></a>Parametry
 `pbstrName`

 [out] Vrátí název vlákna.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Načíst název je vždy název, který je možné zobrazit a popisuje tento název vlákna. Název vlákna mohou být odvozen od za běhu architektury, že podporuje s názvem vláken, nebo může být název odvozený z ladicího stroje. Alternativně lze nastavit název vlákna voláním [setthreadname –](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)