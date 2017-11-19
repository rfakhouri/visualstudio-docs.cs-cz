---
title: IDebugMessageEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMessageEvent2
helpviewer_keywords: IDebugMessageEvent2 interface
ms.assetid: a9ff3d00-e9ac-4cd6-bda9-584a4815aff8
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ecc33a729864fe1fd84c16e732ffceb3b0f858a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmessageevent2"></a>IDebugMessageEvent2
Toto rozhraní používá stroj ladění (DE) k odeslání zprávy do Visual Studia, která vyžaduje odpověď od uživatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMessageEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní k odeslání zprávy do Visual Studia, která vyžaduje odpověď uživatele. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní.  
  
 Implementace tohoto rozhraní musí komunikovat Visual Studio volání [SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md) k DE. Například to můžete provést zprávou odesílat zprávy je DE zpracování vláken, nebo objekt implementace tohoto rozhraní by mohla obsahovat odkaz na DE a zpětné volání je DE s odpovědí předaný do `IDebugMessageEvent2::SetResponse`.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událostí k zobrazení zprávy pro uživatele, který vyžaduje odpověď. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k programu laděné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugMessageEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)|Získá zprávu, která se má zobrazit.|  
|[SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md)|Nastaví odpověď, pokud existuje, v rozevíracím seznamu zpráv.|  
  
## <a name="remarks"></a>Poznámky  
 DE bude používat toto rozhraní, pokud to vyžaduje konkrétní odpověď od uživatele pro danou zprávu. Například pokud je DE získá zprávu "Přístup byl odepřen" po pokusu o vzdáleně připojit k programu, DE odešle tato konkrétní zpráva k sadě Visual Studio v `IDebugMessageEvent2` událost s styl box zpráva `MB_RETRYCANCEL`. To umožňuje uživateli opakovat nebo ukončit v operaci připojení.  
  
 DE Určuje, jak se tato zpráva je zpracovávat souladu s konvencemi prostředí Win32 funkce `MessageBox` (viz [AfxMessageBox –](http://msdn.microsoft.com/Library/d66d0328-cdcc-48f6-96a4-badf089099c8) podrobnosti).  
  
 Použití [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) rozhraní pro odesílání zpráv pro Visual Studio, které nevyžadují odpověď od uživatele.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)