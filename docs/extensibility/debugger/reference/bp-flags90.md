---
title: BP_FLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: af59e06ad31b56c04127ca89b43a903db36d3615
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)