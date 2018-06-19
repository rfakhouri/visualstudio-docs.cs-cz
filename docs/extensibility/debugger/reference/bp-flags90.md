---
title: BP_FLAGS90 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9f8153f3fb2419e26f7e7d3a741ae4c79c9272a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100345"
---
# <a name="bpflags90"></a>BP_FLAGS90
Vytvoří výčet platné hodnoty pro volitelné příznaky. Volitelné příznaky lze určit další informace, když nastavit zarážky. Tento výčet rozšiřuje [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```csharp  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 BP90_FLAG_NONE  
 Určuje bez zarážek příznak.  
  
 BP90_FLAG_MAP_DOCPOSITION  
 Určuje, že modul ladění (DE) by měla být mapována zarážce pomocí pozice dokumentu. To se vztahuje pouze na body přerušení nastavené v orientované skriptu zdrojové soubory jako je například stránky ASP (Active Server).  
  
 BP90_FLAG_DONT_STOP  
 Určuje, že zarážce měla by být zpracována modul ladění, ale, modul ladění nakonec nesmí zastavit To znamená [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) objekt události by se neměly posílat. Tento příznak je určen k použití především s body trasování.  
  
 BP90_FLAG_TRACEPOINT_CONTINUE  
 Chcete-li zjistit, zda je nutné vymazat stav taktování používá stroj nativní ladění. Liší se od BP90_FLAG_DONT_STOP protože BP90_FLAG_DONT_STOP není nastavená, pokud je trasování bod provede makra.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)