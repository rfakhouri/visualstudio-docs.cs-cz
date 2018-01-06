---
title: IDebugCanStopEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCanStopEvent2
helpviewer_keywords: IDebugBreakpointRequest2 interface
ms.assetid: 784bd5b1-4a3f-4455-b313-c4c9a82555a5
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 59e601e828fd3dad1487925c649972efc7b019a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcanstopevent2"></a>IDebugCanStopEvent2
Toto rozhraní umožňuje požádat správce ladicí relace (SDM), zda chcete zastavit aktuální umístění kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCanStopEvent2 : IUknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní pro podporu procházení zdrojového kódu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní (SDM používá [QueryInterface](/cpp/atl/queryinterface) pro přístup k `IDebugEvent2` rozhraní).  
  
 Implementace tohoto rozhraní musí komunikovat SDM volání [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) k modulu ladění. Například to můžete provést zprávou odesílat zprávy ladění modul zpracování vláken, nebo objekt implementace tohoto rozhraní by mohla obsahovat odkaz na modul ladění a zpětného volání do modul ladění s příznakem předaný do `IDebugCanStopEvent2::CanStop`.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE může odesílat tato metoda pokaždé, když je DE se zobrazí výzva, chcete-li pokračovat, spouštění a DE prochází kód. Tato událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytl SDM, pokud je připojené k programu laděné funkce zpětného volání.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugCanStopEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)|Získá důvod pro tuto událost.|  
|[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)|Určuje, zda by měl program laděné zastavit umístění této události (a odeslat událost, která popisuje příčinou zastavení) nebo právě pokračovat v provádění.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)|Získá kontext dokumentu, který popisuje umístění této události.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)|Získá kontext kód, který popisuje umístění této události.|  
  
## <a name="remarks"></a>Poznámky  
 DE odešle toto rozhraní, pokud kroky uživatele do funkce a DE vyhledá žádné informace o ladění existuje nebo informace o ladění existuje, ale je DE nebude vědět, pokud lze zobrazit zdrojový kód pro danou lokalitu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)