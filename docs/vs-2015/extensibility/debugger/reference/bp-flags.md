---
title: BP_FLAGS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_FLAGS
helpviewer_keywords:
- BP_FLAGS enumeration
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b6feb965c564e74dbb026a66a964d233b3ed75fb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629241"
---
# <a name="bpflags"></a>BP_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [BP_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-flags).  
  
Poskytuje volitelné příznaky, které slouží k zadání dalších informací při nastavení zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
typedef DWORD BP_FLAGS;  
```  
  
```csharp  
public enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
```  
  
## <a name="members"></a>Členové  
 BP_FLAG_NONE  
 Určuje příznak bez zarážek.  
  
 BP_FLAG_MAP_DOCPOSITION  
 Určuje, že ladicí stroj (DE) by měla být mapována zarážky pomocí umístění dokumentu. To se vztahuje pouze na zarážky nastavené v skript orientovaného zdrojových souborech, jako je například stránek ASP (Active Server).  
  
 BP_FLAG_DONT_STOP  
 Určuje, že zarážka by měla být zpracovány ladicího stroje, ale, že ladicí stroj nakonec by neměl zastavit existuje (to znamená, [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) objektu události nesmí být rozesílaná). Tento příznak slouží k používá hlavně s zarážky s trasováním.  
  
## <a name="remarks"></a>Poznámky  
 Používá pro `dwFlags` člena [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.  
  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)

