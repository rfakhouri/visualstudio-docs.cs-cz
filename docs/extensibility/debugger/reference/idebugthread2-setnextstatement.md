---
title: IDebugThread2::SetNextStatement | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::SetNextStatement
helpviewer_keywords:
- IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 87a5ba19eed0c0ee4d78feeb755b50db428d77d9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66320092"
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
Nastaví aktuální ukazatel příkazu v kontextu daného kódu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetNextStatement ( 
   IDebugStackFrame2*  pStackFrame,
   IDebugCodeContext2* pCodeContext
);
```

```csharp
int SetNextStatement ( 
   IDebugStackFrame2  pStackFrame,
   IDebugCodeContext2 pCodeContext
);
```

## <a name="parameters"></a>Parametry
`pStackFrame`\
Vyhrazeno pro budoucí použití; Nastavte na hodnotu null.

`pCodeContext`\
[in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který popisuje umístění se pokračovalo v kódu a jeho kontext.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.

|Value|Popis|
|-----------|-----------------|
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|Následující příkaz nelze v zásobníku hlouběji v zásobníku rámce.|
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|Další příkaz není přidružené žádné rámce v zásobníku.|
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|Některé ladicí stroj nelze nastavit další příkaz po výjimce.|

## <a name="remarks"></a>Poznámky
 Ukazatele na instrukci označuje další instrukci nebo příkaz ke spuštění. Tato metoda se používá, zkuste řádek zdrojového kódu nebo vynutit spuštění, abyste mohli pokračovat v jiné funkci, třeba.

## <a name="see-also"></a>Viz také:
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)