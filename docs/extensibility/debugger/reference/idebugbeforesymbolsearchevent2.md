---
title: IDebugBeforeSymbolSearchEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aed9c24717866750c3b9139ab2e04b48d5eda960
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53930931"
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
Ladicí stroj (DE) odešle toto rozhraní Správce ladění relace (SDM) Chcete-li nastavit stav panelu zprávy během načítání symbolů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní, když je nutné nastavit zprávu na stavovém řádku během načítání symbolů. Toto rozhraní je implementováno pouze ladicími stroji, které pracovat, nebo jsou součástí interpretů skriptu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) musí implementovat rozhraní na stejný objekt jako toto rozhraní (SDM používá **QueryInterface** přístup **IDebugEvent2** rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událost, když je nutné nastavit zprávu na stavovém řádku během načítání symbolů. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytnutých SDM při připojení k laděnému programu funkce zpětného volání.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugBeforeSymbolSearchEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|Načte název modulu, která se právě ladí.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll