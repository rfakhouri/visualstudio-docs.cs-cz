---
title: EVENTATTRIBUTES | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3026845be9aa6623d6c5cd42406385e8c5c2a11e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149379"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje atributy události.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>Členové  
 EVENT_ASYNCHRONOUS  
 Označuje, že událost je asynchronní a je potřeba žádná odpověď na události.  
  
 EVENT_SYNCHRONOUS  
 Označuje, že událost je synchronní; Odpovědět prostřednictvím [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT_STOPPING  
 Označuje, že se jedná o událostí ukončení. Musí být kombinován se buď `EVENT_ASYNCHRONOUS` nebo `EVENT_SYNCHRONOUS`.  
  
 EVENT_ASYNC_STOP  
 Označuje asynchronní zastavení událost. Aktuálně neexistuje žádná taková událost. Tento příznak je jen zástupný symbol.  
  
 EVENT_SYNC_STOP  
 Označuje událostí synchronní ukončení (kombinace `EVENT_SYNCHRONOUS` a `EVENT_STOPPING`). Tato hodnota se používá modul ladění (DE) při odesílání událostí ukončení. Odpověď se provádí prostřednictvím volání [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [krok](../../../extensibility/debugger/reference/idebugprogram2-step.md), nebo [pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT_IMMEDIATE  
 Určuje události, které je odesláno okamžitě a synchronně integrovaného vývojového prostředí. Tento příznak číslo zkombinuje s další příznaky jako `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, nebo `EVENT_SYNC_STOP` označující typ události a fakt, že se označuje mechanismus odpověď (pokud existuje).  
  
 EVENT_EXPRESSION_EVALUATION  
 Událost je výsledkem vyhodnocení výrazu.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány v `dwAttrib` parametr [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metody.  
  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
