---
title: DISASSEMBLY_STREAM_SCOPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_STREAM_SCOPE
helpviewer_keywords:
- DISASSEMBLY_STREAM_SCOPE enumeration
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 57a8741720cda263a399088848fcaa1862a2ff4e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53919200"
---
# <a name="disassemblystreamscope"></a>DISASSEMBLY_STREAM_SCOPE
Určuje rozsah datového proudu zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## <a name="members"></a>Členové  
 DSS_HUGE  
 Určuje, že rozložení kontext kódu bude generovat výstup více než klient by obvykle chcete načíst v jednom volání.  
  
 DSS_FUNCTION  
 Určuje, že funkce obsažené v kontextech kód zpětně překládán. Určuje, že datový proud zpětný překlad představuje funkci, pokud vrátí [getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) metody.  
  
 DSS_MODULE  
 Pokud vrátí `IDebugDisassemblyStream2::GetScope` metody Určuje, že datový proud zpětný překlad představuje modul.  
  
 DSS_ALL  
 Určuje zpětný překlad pro celý adresní prostor.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) – metoda a vrácené [getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) metoda.  
  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)