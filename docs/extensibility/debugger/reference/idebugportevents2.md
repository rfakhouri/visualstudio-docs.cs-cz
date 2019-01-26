---
title: IDebugPortEvents2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortEvents2
helpviewer_keywords:
- IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 860b03b26c9da4975d4482412214dcc69199de47
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54985143"
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
Toto rozhraní upozorní naslouchací proces (obvykle správce ladění relace [SDM] nebo ladicí stroj) z procesu a program vytváření a ničení na konkrétním portu. Tyto informace slouží k zobrazení v reálném čase přehled procesů a programy spuštěné na portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle implementuje toto rozhraní k přijímání oznámení o program vytváření a zničení. Ladicí stroj, můžete taky implementovat toto rozhraní tak, aby naslouchala událostem těchto portů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Všechny [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní je možné zadávat dotazy pro <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní. Pak bude <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> metodu `IDebugPortEvents2` je volána <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní pro získání <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní. Nakonec <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> metoda ve <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní je volána k odesílání událostí přes [události](../../../extensibility/debugger/reference/idebugportevents2-event.md) metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody `IDebugPortEvents2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)|Odesílá události, které popisují vytváření a ničení procesy a programů na portu.|  
  
## <a name="remarks"></a>Poznámky  
 `IDebugPortEvents2` také používá SDM ladit programy, které běží v procesu, který je již laděn.  
  
 Port události jsou předány SDM tímto rozhraním.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)