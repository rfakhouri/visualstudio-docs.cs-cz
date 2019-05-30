---
title: IDebugProcess2::CauseBreak | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::CauseBreak
helpviewer_keywords:
- IDebugProcess2::CauseBreak
ms.assetid: efda8865-2319-4d53-90bf-6d9d74cd5195
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fbe4f3cac40306467e6efc7d87ca860a6d6f3f0e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353233"
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

## <a name="see-also"></a>Viz také:
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)