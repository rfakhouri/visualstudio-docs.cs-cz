---
title: Iremotedebugapplication – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication interface
ms.assetid: 96bf2a3f-049f-46ba-86ad-57fc184343a2
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a231818def210f7c88ab031059f8561c67b33d1
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58159150"
---
# <a name="iremotedebugapplication-interface"></a>IRemoteDebugApplication – rozhraní
Představuje běžící aplikaci. Nemusí se tak, aby odpovídaly k procesu operačního systému. Ladicí program obvykle, zaměřuje na aplikace pro ladění. Správce ladění procesu obvykle implementují objektu aplikace.  
  
 Kromě metod zděděných z `IUnknown`, `IRemoteDebugApplication` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IRemoteDebugApplication::ResumeFromBreakPoint](../../winscript/reference/iremotedebugapplication-resumefrombreakpoint.md)|Pokračuje v aplikaci, která je aktuálně v zarážku.|  
|[IRemoteDebugApplication::CauseBreak](../../winscript/reference/iremotedebugapplication-causebreak.md)|Způsobí, že aplikace do ladicího programu při nejbližší příležitosti.|  
|[IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)|Ladicí program připojí k této aplikaci.|  
|[IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md)|Aktuální ladicí program se odpojí z aplikace.|  
|[IRemoteDebugApplication::GetDebugger](../../winscript/reference/iremotedebugapplication-getdebugger.md)|Vrátí aktuální ladicí program připojen k aplikaci.|  
|[IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md)|Poskytuje mechanismus pro ladicí program IDE, pracovat na více instancí procesu do aplikace, k vytváření objektů v procesu aplikace.|  
|[IRemoteDebugApplication::QueryAlive](../../winscript/reference/iremotedebugapplication-queryalive.md)|Určuje, zda je interaktivní aplikace.|  
|[IRemoteDebugApplication::EnumThreads](../../winscript/reference/iremotedebugapplication-enumthreads.md)|Vytvoří výčet všech vláken, které jsou známé jako spojený s aplikací.|  
|[IRemoteDebugApplication::GetName](../../winscript/reference/iremotedebugapplication-getname.md)|Vrátí název tohoto uzlu aplikace.|  
|[IRemoteDebugApplication::GetRootNode](../../winscript/reference/iremotedebugapplication-getrootnode.md)|Vrátí uzel aplikace, ve které se přidají všechny uzly, které jsou přidružené k aplikaci.|  
|[IRemoteDebugApplication::EnumGlobalExpressionContexts](../../winscript/reference/iremotedebugapplication-enumglobalexpressioncontexts.md)|Vytvoří výčet kontexty globální výraz pro všechny jazyky, které jsou spuštěné v této aplikaci.|