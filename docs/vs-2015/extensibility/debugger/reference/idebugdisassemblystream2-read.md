---
title: IDebugDisassemblyStream2::Read | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::Read
helpviewer_keywords:
- IDebugDisassemblyStream2::Read
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 520c801a0603f2c6d3228ae95ad144827eac0088
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203010"
---
# <a name="idebugdisassemblystream2read"></a>IDebugDisassemblyStream2::Read
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Přečte pokyny od aktuální pozice v datovém proudu zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [Getsize –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)   
 [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)
