---
title: Idebugapplication – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication interface
ms.assetid: 5dfa941b-4cd9-46fa-a230-3f41df9ea205
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8229f234f8a8ce607f36c48e070cb3d40a211d45
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62990829"
---
# <a name="idebugapplication-interface"></a>IDebugApplication – rozhraní
Zpřístupňuje bez vzdáleného ladění metody pro použití s moduly jazyka a hostitele.  
  
 Kromě metod zděděných z `IRemoteDebugApplication`, `IDebugApplication` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplication::SetName](../../winscript/reference/idebugapplication-setname.md)|Nastaví název aplikace.|  
|[IDebugApplication::StepOutComplete](../../winscript/reference/idebugapplication-stepoutcomplete.md)|Upozorní správce ladění procesu, že modul jazyka v režimu krokování se chystá vrátí výsledek volajícímu.|  
|[IDebugApplication::DebugOutput](../../winscript/reference/idebugapplication-debugoutput.md)|Způsobí, že daný řetězec, který se má zobrazit ladicím programem integrovaného vývojového prostředí.|  
|[IDebugApplication::StartDebugSession](../../winscript/reference/idebugapplication-startdebugsession.md)|Spustí ladicí program výchozí prostředí IDE a připojí ladicí relace pro tuto aplikaci, pokud už není připojen.|  
|[IDebugApplication::HandleBreakPoint](../../winscript/reference/idebugapplication-handlebreakpoint.md)|Způsobí, že chcete blokovat aktuální vlákno a odešle oznámení této zarážky v ladicím programu integrovaného vývojového prostředí.|  
|[IDebugApplication::Close](../../winscript/reference/idebugapplication-close.md)|Způsobí, že tato aplikace uvolnit všechny odkazy a zadejte neaktivním stavu.|  
|[IDebugApplication::GetBreakFlags](../../winscript/reference/idebugapplication-getbreakflags.md)|Vrátí aktuální break příznaky pro aplikaci.|  
|[IDebugApplication::GetCurrentThread](../../winscript/reference/idebugapplication-getcurrentthread.md)|Vrátí vlákno přidružené k aktuálně běžícímu vláknu.|  
|[IDebugApplication::CreateAsyncDebugOperation](../../winscript/reference/idebugapplication-createasyncdebugoperation.md)|Poskytuje asynchronní přístup k dané ladění synchronní operace.|  
|[IDebugApplication::AddStackFrameSniffer](../../winscript/reference/idebugapplication-addstackframesniffer.md)|Přidá zprostředkovatele enumerátor rámec zásobníku do této aplikace.|  
|[IDebugApplication::RemoveStackFrameSniffer](../../winscript/reference/idebugapplication-removestackframesniffer.md)|Odebere poskytovatele enumerátor rámce zásobníku z této aplikace.|  
|[IDebugApplication::QueryCurrentThreadIsDebuggerThread](../../winscript/reference/idebugapplication-querycurrentthreadisdebuggerthread.md)|Určuje, zda je aktuální vlákno spuštěné vlákno ladicího programu.|  
|[IDebugApplication::SynchronousCallInDebuggerThread](../../winscript/reference/idebugapplication-synchronouscallindebuggerthread.md)|Poskytuje mechanismus pro volající ke spouštění kódu v vlákno ladicího programu.|  
|[IDebugApplication::CreateApplicationNode](../../winscript/reference/idebugapplication-createapplicationnode.md)|Vytvoří nový uzel aplikace, která souvisí s určitým dokumentem zprostředkovatele.|  
|[IDebugApplication::FireDebuggerEvent](../../winscript/reference/idebugapplication-firedebuggerevent.md)|Aktivuje se v generických událostí v ladicím programu `IApplicationDebugger` rozhraní.|  
|[IDebugApplication::HandleRuntimeError](../../winscript/reference/idebugapplication-handleruntimeerror.md)|Způsobí, že chcete blokovat aktuální vlákno a odešle oznámení o chybě integrovaného vývojového prostředí v ladicím programu.|  
|[IDebugApplication::FCanJitDebug](../../winscript/reference/idebugapplication-fcanjitdebug.md)|Určuje, zda je zaregistrován ladicí program just-in-time (JIT).|  
|[IDebugApplication::FIsAutoJitDebugEnabled](../../winscript/reference/idebugapplication-fisautojitdebugenabled.md)|Určuje, zda JIT ladící program registrován vlečný hostitelům automatického ladění.|  
|[IDebugApplication::AddGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-addglobalexpressioncontextprovider.md)|Přidá zprostředkovatele kontextu globální výraz do této aplikace.|  
|[IDebugApplication::RemoveGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-removeglobalexpressioncontextprovider.md)|Poskytovatel kontextu globální výraz odebere z této aplikace.|