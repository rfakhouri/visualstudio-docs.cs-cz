---
title: IDebugDisassemblyStream2::Read | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::Read
helpviewer_keywords:
- IDebugDisassemblyStream2::Read
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eb204ccb98d0c7f5a6f5eeac9ccbc5ea07dfae16
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688456"
---
# <a name="idebugdisassemblystream2read"></a>IDebugDisassemblyStream2::Read
Přečte pokyny od aktuální pozice v datovém proudu zpětný překlad.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Read( 
   DWORD                     dwInstructions,
   DISASSEMBLY_STREAM_FIELDS dwFields,
   DWORD*                    pdwInstructionsRead,
   DisassemblyData*          prgDisassembly
);
```

```csharp
int Read( 
   uint                           dwInstructions,
   enum_DISASSEMBLY_STREAM_FIELDS dwFields,
   out uint                       pdwInstructionsRead,
   DisassemblyData[]              prgDisassembly
);
```

#### <a name="parameters"></a>Parametry
 `dwInstructions`

 [in] Počet instrukcí pro převod ze strojového kódu. Tato hodnota je taky maximální délka `prgDisassembly` pole.

 `dwFields`

 [in] Kombinace příznaků z [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) výčet důvody, které pole `prgDisassembly` mají doplnit.

 `pdwInstructionsRead`

 [out] Vrátí počet instrukcí ve skutečnosti zpětně překládán.

 `prgDisassembly`

 [out] Pole [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktury, které se vyplní zpětně přeložený kód jednu strukturu za zpětně přeložený instrukce. Délka tohoto pole závisí `dwInstructions` parametru.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Maximální počet pokyny, které jsou k dispozici v aktuálním oboru, které lze získat voláním [getsize –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md) metody.

 Aktuální pozici, kde je další instrukci čtení z lze změnit pomocí volání [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) metoda.

 `DSF_OPERANDS_SYMBOLS` Příznak lze přidat do `DSF_OPERANDS` příznak v `dwFields` parametr k označení, že názvy symbolů má být použit při zpětném překladu pokyny.

## <a name="see-also"></a>Viz také
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
- [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)
- [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)