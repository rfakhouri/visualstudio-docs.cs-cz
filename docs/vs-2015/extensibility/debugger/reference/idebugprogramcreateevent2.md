---
title: IDebugProgramCreateEvent2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramCreateEvent2
helpviewer_keywords:
- IDebugProgramCreateEvent2 interface
ms.assetid: b19a7934-6179-4a68-9075-bd7dcd640b05
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 24a1a1942031dac71ddad7b528f0e5df161c629e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148616"
---
# <a name="idebugprogramcreateevent2"></a>IDebugProgramCreateEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní je odeslaný ladicího stroje (DE) pro správce ladění relace (SDM) při program je připojen k.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE nebo dodavatele port. Tento vlastní port implementuje toto rozhraní oznamuje, že program vytvořil, obvykle v okamžiku, kdy program je připojen k. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM `QueryInterface` metody přístup `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE nebo dodavatele port. Tento vlastní port vytvoří a odešle tento objekt událostí k vytváření sady sestav. DE posílání této události [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k laděnému programu. Dodavatel port. Tento vlastní port odešle pomocí této události [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) rozhraní.  
  
## <a name="remarks"></a>Poznámky  
 DE nebo dodavatele port. Tento vlastní port publikuje novou [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní voláním [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
