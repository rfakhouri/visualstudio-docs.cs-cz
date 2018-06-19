---
title: DISASSEMBLY_STREAM_SCOPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: a0c72d0f14da9840c0a77d5ae88cb0acb5b54cba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102064"
---
# <a name="disassemblystreamscope"></a>DISASSEMBLY_STREAM_SCOPE
Určuje obor datového proudu zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## <a name="members"></a>Členové  
 DSS_HUGE  
 Určuje, že rozložení obsahu kódu by generovat výstup více než obvykle potřebujete načíst v jediném volání klienta.  
  
 DSS_FUNCTION  
 Určuje, že by měl rozložit funkce obsažený v kontextu kódu. Určuje, že datový proud zpětný překlad představuje funkci, pokud vrácený [getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) metoda.  
  
 DSS_MODULE  
 Když vrácený `IDebugDisassemblyStream2::GetScope` metoda, určuje, že datový proud zpětný překlad představuje modul.  
  
 DSS_ALL  
 Určuje zpětný překlad pro celého adresního prostoru.  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) metoda a vrácené [getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) metoda.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [Getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)