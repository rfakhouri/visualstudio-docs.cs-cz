---
title: IDebugThread2::CanSetNextStatement | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::CanSetNextStatement
helpviewer_keywords:
- IDebugThread2::CanSetNextStatement
ms.assetid: 7014af80-ff4f-4790-a34b-0528918d1fa3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 43ec2c5d157832834f76834f7b93e193629b66d8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868380"
---
# <a name="idebugthread2cansetnextstatement"></a>IDebugThread2::CanSetNextStatement
Určuje, zda aktuální ukazatel příkazu může být nastaven na daném zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CanSetNextStatement ( 
   IDebugStackFrame2*  pStackFrame,
   IDebugCodeContext2* pCodeContext
);
```

```csharp
int CanSetNextStatement ( 
   IDebugStackFrame2  pStackFrame,
   IDebugCodeContext2 pCodeContext
);
```

#### <a name="parameters"></a>Parametry
 `pStackFrame` Vyhrazeno pro budoucí použití; Nastavte na hodnotu null. Pokud je hodnota null, použijte aktuální rámec zásobníku.

 `pCodeContext`

 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který popisuje umístění se pokračovalo v kódu a jeho kontext.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud tato metoda vrátí `S_OK`, zavolejte [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md) metoda ve skutečnosti nastavení dalšího příkazu.

## <a name="see-also"></a>Viz také
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)