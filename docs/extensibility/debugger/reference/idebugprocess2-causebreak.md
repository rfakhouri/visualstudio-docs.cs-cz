---
title: IDebugProcess2::CauseBreak | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::CauseBreak
helpviewer_keywords:
- IDebugProcess2::CauseBreak
ms.assetid: efda8865-2319-4d53-90bf-6d9d74cd5195
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a85ab02bce7e1748e769694ee8e06e7898ba2ffb
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695762"
---
# <a name="idebugprocess2causebreak"></a>IDebugProcess2::CauseBreak
Požadavky na další program, který je spuštěním kódu v tomto procesu zastaví a odeslat [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) objektu události.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CauseBreak( 
   void
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)