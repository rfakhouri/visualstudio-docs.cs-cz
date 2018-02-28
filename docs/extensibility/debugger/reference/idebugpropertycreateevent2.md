---
title: IDebugPropertyCreateEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPropertyCreateEvent2
helpviewer_keywords:
- IDebugPropertyCreateEvent2 interface
ms.assetid: 33b3082b-a42e-488a-a1e4-dadf506f922c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0557fd39d21415dfddb1a571c4f9e6ee69badf10
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpropertycreateevent2"></a>IDebugPropertyCreateEvent2
Toto rozhraní zasílá modul ladění (DE) zadaný pro relaci ladění správce (SDM) při vytváření vlastnosti, která je přidružena k určité dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPropertyCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní informuje, zda byl vytvořen vlastnost. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní. Toto rozhraní je implementováno, pokud je DE vytvořil vlastnost přidružený ke skriptu, který byl načteny nebo vytvořili, a pokud skriptu je potřeba se zobrazí v prostředí IDE.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí do sestavy, kterou vytvořil vlastnost. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k programu laděné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metodě `IDebugPropertyCreateEvent2` rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md)|Získá novou vlastnost.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud vlastnost obsahuje konkrétní dokument nebo skript s ním spojená, DE můžete odeslat tuto událost SDM za účelem aktualizace **dokumentů skriptu** okno s název dokumentu. Zavolá SDM [GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md) s argumentem `guidDocument` načíst `VARIANT` obsahující [IUnknown](/cpp/atl/iunknown) ukazatel. Zavolá SDM [QueryInterface](/cpp/atl/queryinterface) na tento ukazatel načíst [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní, které se používá k aktualizaci **dokumentů skriptu** okno.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)