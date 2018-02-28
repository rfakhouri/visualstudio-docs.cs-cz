---
title: IDebugProgram2::GetDisassemblyStream | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgram2::GetDisassemblyStream
helpviewer_keywords:
- IDebugProgram2::GetDisassemblyStream
ms.assetid: beda0da5-267e-4bf3-96c4-b659d29e2254
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: db2f0855ecb22a711fa525a6a85e3f445af28d0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2getdisassemblystream"></a>IDebugProgram2::GetDisassemblyStream
Získá datový proud zpětný překlad pro tento program nebo jeho část tohoto programu.  
  
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
  
#### <a name="parameters"></a>Parametry  
 `dwScope`  
 [v] Určuje hodnotu z [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) výčet, který definuje rozsah datového proudu zpětný překlad.  
  
 `pCodeContext`  
 [v] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který představuje pozici s začínají datový proud zpětný překlad.  
  
 `ppDisassemblyStream`  
 [out] Vrátí [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) objekt, který představuje datový proud zpětný překlad.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `E_DISASM_NOTSUPPORTED` pokud zpětný překlad není podporovaná pro tento konkrétní architekturu.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `dwScopes` parametr má `DSS_HUGE` příznak [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) nastavte výčet a pak se očekává, že zpětný překlad vrátí velký počet zpětný překlad pokyny, například pro celý soubor nebo modul. Pokud `DSS_HUGE` není nastaven příznak a pak se očekává, že zpětný překlad omezit na malé oblasti, obvykle u jedné funkce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)