---
title: IDebugEngine3 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine3
helpviewer_keywords:
- IDebugEngine3 interface
ms.assetid: 8bdf4bb7-3b5d-4991-8981-772d4f6bb656
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c043a05d2656dc1cc56377ad061854cd1aca9e7c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920853"
---
# <a name="idebugengine3"></a>IDebugEngine3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Představuje jeden ladicího stroje (DE), který řídí ladění jednoho nebo více modulů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngine3 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementují vlastní DE (pokud ji podporuje symboly) umožňující stav JustMyCode. Pomocí DE musí implementovat toto rozhraní, pokud ji podporuje, symboly a JustMyCode.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je volán Správce ladění relace (SDM) k předání na možností uživatele pro umístění, ze kterých se načíst symboly. Nazývá se také nastavit GUID modul, když je vytvořena instance (Tento identifikátor GUID je založená na metriky od okamžiku modul registrace). SDM také volá tato rozhraní se nastavit stav JustMyCode a nastavit všechny výjimky známé ladicí program do zadaného stavu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděných z [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md), `IDebugEngine3` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)|Nastaví cestu nebo cesty, které je DE budete používat pro hledání pro symboly ladění.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)|Načte symboly pro všechny moduly, u kterých ještě nedošlo jejich načteny symboly.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)|DE informuje o JustMyCode informace.|  
|[SetEngineGuid](../../../extensibility/debugger/reference/idebugengine3-setengineguid.md)|Nastaví DE GUID z metriky.|  
|[SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)|Nastavení aktuálně nejsou dokončeny všechny výjimky do zadaného stavu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
