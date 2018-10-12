---
title: BP_UNBOUND_REASON | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4d6060753a3208fd09485a52d0959daf31f6c3e0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49250663"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Poskytuje z důvodů, proč nevázaná zarážku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```csharp  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## <a name="members"></a>Členové  
 BPUR_UNKNOWN  
 Důvodem neznámý.  
  
 BPUR_CODE_UNLOADED  
 Kód, který obsahuje zarážku byl uvolněn.  
  
 BPUR_BREAKPOINT_REBIND  
 Zarážku bylo znovu připojeno, do jiného umístění. To může dojít po úpravě a pokračovat v operacích přesun zarážku nebo zarážku je vázán na soubor s cestou, která již není platný.  
  
 BPUR_ BREAKPOINT_ERROR  
 Zarážka je určena jako chybu po je vázán. K tomu dochází na spravovaných zarážky, jejíž podmínky už nejsou platné.  
  
## <a name="remarks"></a>Poznámky  
 Vrácené [getreason –](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)

