---
title: IDebugOutputStringEvent2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugOutputStringEvent2
helpviewer_keywords:
- IDebugOutputStringEvent2 interface
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 844d93a6752538c6b7239b6c10688fdfbd98b401
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65695193"
---
# <a name="idebugoutputstringevent2"></a>IDebugOutputStringEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní je odeslaný ladicího stroje (DE) pro správce ladění relace (SDM) do výstupního řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní lze odeslat řetězec k **výstup** okno integrovaného vývojového prostředí. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) přístup `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle objekt této události lze odeslat řetězec k **výstup** okna. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který je poskytnut pomocí SDM, když je připojen k laděnému programu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody `IDebugOutputStringEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetString](../../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)|Získá zobrazitelný zprávu.|  
  
## <a name="remarks"></a>Poznámky  
 Například v nespravovaném kódu můžou pocházet řetězec, který má být výstup při laděnému programu odešle řetězec Win32 `OutputDebugString` funkce. Tento řetězec je zachycen DE a dostanou k SDM jako `IDebugOutputStringEvent2` událostí.  
  
 Použití [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md) odeslat zprávu, která vyžaduje odpověď uživatele.  
  
 Použití [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) odeslat chybovou zprávu, která nevyžaduje odpověď.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
