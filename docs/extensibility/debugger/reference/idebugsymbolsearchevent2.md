---
title: IDebugSymbolSearchEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugSymbolSearchEvent2
helpviewer_keywords: IDebugSymbolSearchEvent2
ms.assetid: 9b946d55-ff85-44eb-b40a-efbf8282eafd
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a931768dd13f2ced30f329b54c1fe6eb9333eb9c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsymbolsearchevent2"></a>IDebugSymbolSearchEvent2
Toto rozhraní odesílají modul ladění (DE) k označení, že symboly pro ladění pro modul laděné byly načteny.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní informuje, aby byly načteny modul symboly. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí informuje, aby byly načteny modul symboly. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při jej připojit k programu laděné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 `IDebugSymbolSearchEvent2` Rozhraní zpřístupní metodu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getsymbolsearchinfo –](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)|Načte informace o výsledcích hledání symbolu.|  
  
## <a name="remarks"></a>Poznámky  
 Tato událost bude odeslána, i když symboly se nepodařilo načíst. Volání metody `IDebugSymbolSearchEvent2::GetSymbolSearchInfo` umožňuje obslužná rutina tuto událost, chcete-li zjistit, zda modul ve skutečnosti žádné symboly.  
  
 Visual Studio se většinou používá tato událost se bude aktualizovat stav načíst symboly v **moduly** okno.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)