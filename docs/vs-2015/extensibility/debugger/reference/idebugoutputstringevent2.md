---
title: IDebugOutputStringEvent2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugOutputStringEvent2
helpviewer_keywords:
- IDebugOutputStringEvent2 interface
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cceb929a7f75420e1b93f15d653a48c1e112798e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678702"
---
# <a name="idebugoutputstringevent2"></a>IDebugOutputStringEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugOutputStringEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugoutputstringevent2).  
  
Toto rozhraní je odeslaný ladicího stroje (DE) pro správce ladění relace (SDM) do výstupního řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní lze odeslat řetězec k **výstup** okno integrovaného vývojového prostředí. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) přístup `IDebugEvent2` rozhraní.  
  
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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)

