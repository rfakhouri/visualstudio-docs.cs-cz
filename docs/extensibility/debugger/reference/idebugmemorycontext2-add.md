---
title: IDebugMemoryContext2::Add | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c1cafbf22e51f867948491e2925c085bd387ea84
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347093"
---
# <a name="idebugmemorycontext2add"></a>IDebugMemoryContext2::Add
Přidá zadanou hodnotu k aktuálnímu kontextu a vrátí nový kontext.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Add( 
   UINT64                 dwCount,
   IDebugMemoryContext2** ppMemCxt
);
```

```csharp
int Add(
   ulong                    dwCount,
   out IDebugMemoryContext2 ppMemCxt
);
```

## <a name="parameters"></a>Parametry
`dwCount`\
[in] Hodnota k přidání do aktuálního kontextu.

`ppMemCxt`\
[out] Vrátí nový [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objektu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Místní paměť je adresa, tak přínos pro adresu vytvoří novou adresu, která vyžaduje nové rozhraní kontextu.

 Tato metoda musí vždy vytvořila nový kontext, i když Výsledná adresa je mimo paměť spojený s tímto kontextem. Jedinou výjimkou je, pokud je možné přidělit paměti pro nový kontext nebo pokud `ppMemCxt` je hodnota null (což je chybu).

## <a name="see-also"></a>Viz také:
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)