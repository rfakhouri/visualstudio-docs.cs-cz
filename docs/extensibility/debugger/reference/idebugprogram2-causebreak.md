---
title: IDebugProgram2::CauseBreak | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a01b5982b4f747bd70c3a35bc0b7191bb54cd21b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311347"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
Požadavky, že program zastavit provádění na další čas, po jednu z jeho vlákna pokusy o spuštění.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CauseBreak( 
   void 
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) události se odešle, když program dále pokusí o spuštění kódu po volání této metody.

 Tato metoda je asynchronní metoda vrátí hodnotu okamžitě bez nutně čekání na ukončení programu.

## <a name="see-also"></a>Viz také:
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)