---
title: IDebugDisassemblyStream2::Seek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e97da5b4b65b18c9d4c745dea2cb5f0915862731
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66310359"
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
Přesune ukazatel čtení ve službě stream zpětný překlad daný počet instrukcí vzhledem k zadané pozici.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Seek( 
   SEEK_START          dwSeekStart,
   IDebugCodeContext2* pCodeContext,
   UINT64              uCodeLocationId,
   INT64               iInstructions
);
```

```csharp
int Seek( 
   enum_SEEK_START    dwSeekStart,
   IDebugCodeContext2 pCodeContext,
   ulong              uCodeLocationId,
   long               iInstructions
);
```

## <a name="parameters"></a>Parametry
`dwSeekStart`\
[in] Hodnota z [SEEK_START](../../../extensibility/debugger/reference/seek-start.md) výčet, který určuje relativní umístění a spusťte proces hledání.

`pCodeContext`\
[in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) představující kontext kódu, který je operace seek vzhledem k objektu. Tento parametr se používá jenom v případě `dwSeekStart`  =  `SEEK_START_CODECONTEXT`; v opačném případě tento parametr je ignorován a může mít hodnotu null.

`uCodeLocationId`\
[in] Identifikátor umístění kódu, který je operace seek vzhledem k. Tento parametr se používá, pokud `dwSeekStart`  =  `SEEK_START_CODELOCID`; v opačném případě tento parametr je ignorován a je možné nastavit na hodnotu 0. V části poznámky [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) metoda popis identifikátor umístění kódu.

`iInstructions`\
[in] Počet instrukcí přesunout vzhledem k pozice zadané v `dwSeekStart`. Tato hodnota může být záporná hodnota, při přesunutí zpětně.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud hledání pozice na místo mimo seznamu k dispozici pokyny. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud bylo hledání pozice před začátek seznamu, pozici pro čtení je nastaven na první instrukce v seznamu. Pokud se na místo na konci seznamu, pozici pro čtení nastavená na poslední instrukce v seznamu.

## <a name="see-also"></a>Viz také:
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)