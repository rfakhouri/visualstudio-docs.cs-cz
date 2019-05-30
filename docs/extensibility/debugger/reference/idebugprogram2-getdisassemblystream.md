---
title: IDebugProgram2::GetDisassemblyStream | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetDisassemblyStream
helpviewer_keywords:
- IDebugProgram2::GetDisassemblyStream
ms.assetid: beda0da5-267e-4bf3-96c4-b659d29e2254
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 71389ef210d50becaab4d25e29194c2a40000497
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66308764"
---
# <a name="idebugprogram2getdisassemblystream"></a>IDebugProgram2::GetDisassemblyStream
Získá datový proud zpětný překlad pro tento program nebo součástí tohoto programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDisassemblyStream( 
   DISASSEMBLY_STREAM_SCOPE   dwScope,
   IDebugCodeContext2*        pCodeContext,
   IDebugDisassemblyStream2** ppDisassemblyStream
);
```

```csharp
int GetDisassemblyStream( 
   enum_DISASSEMBLY_STREAM_SCOPE  dwScope,
   IDebugCodeContext2             pCodeContext,
   out IDebugDisassemblyStream2   ppDisassemblyStream
);
```

## <a name="parameters"></a>Parametry
`dwScope`\
[in] Určuje hodnotu z [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) výčet, který definuje rozsah datového proudu zpětný překlad.

`pCodeContext`\
[in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který reprezentuje pozice kde začít streamu zpětný překlad.

`ppDisassemblyStream`\
[out] Vrátí [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) objekt, který představuje datový proud zpětný překlad.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_DISASM_NOTSUPPORTED` Pokud pro tuto konkrétní architekturu není podporován převod do strojového jazyka.

## <a name="remarks"></a>Poznámky
 Pokud `dwScopes` parametr má `DSS_HUGE` příznak [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) nastavte výčet a pak zpětného překladu se očekává navrácení velkého počtu pokynů zpětný překlad, například pro celý soubor nebo modulu. Pokud `DSS_HUGE` není nastaven příznak a zpětný má být omezeny na malé oblast obvykle u jedné funkce.

## <a name="see-also"></a>Viz také:
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)