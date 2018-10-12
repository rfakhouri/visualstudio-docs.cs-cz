---
title: IDebugPortEvents2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortEvents2
helpviewer_keywords:
- IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1e0d5a55dd6e6f7b227477b20af4718001ab5a70
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49178903"
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)

