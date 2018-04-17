---
title: BPRESI_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1b6ecfd729762944bcf26814e735c4c73841e2d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="bpresifields"></a>BPRESI_FIELDS
Určuje informace, které mají být načteny o úspěšné rozlišení zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BPRESI_FIELDS {   
   BPRESI_BPRESLOCATION = 0x0001,  
   BPRESI_PROGRAM       = 0x0002,  
   BPRESI_THREAD        = 0x0004,  
   BPRESI_ALLFIELDS     = 0xffffffff  
};  
typedef DWORD BPRESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPRESI_FIELDS {   
   BPRESI_BPRESLOCATION = 0x0001,  
   BPRESI_PROGRAM       = 0x0002,  
   BPRESI_THREAD        = 0x0004,  
   BPRESI_ALLFIELDS     = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 BPRESI_BPRESLOCATION  
 Inicializovat nebo použití `bpResLocation` (zarážek umístění řešení) pole [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktury.  
  
 BPRESI_PROGRAM  
 Inicializace nebo použití `pProgram` pole z `BP_RESOLUTION_INFO` struktura.  
  
 BPRESI_THREAD  
 Inicializace nebo použití `pThread` pole z `BP_RESOLUTION_INFO` struktura.  
  
 BPRESI_ALLFIELDS  
 Určuje všechna pole.  
  
## <a name="remarks"></a>Poznámky  
 Předaný [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) metoda označíte, které pole [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktura mají být inicializován.  
  
 Tyto příznaky se také používají k označení které pole `BP_RESOLUTION_INFO` struktura jsou používané a platné, pokud je vrácen této struktury.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)