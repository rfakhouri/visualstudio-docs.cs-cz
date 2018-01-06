---
title: IDebugPortEvents2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortEvents2
helpviewer_keywords: IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0a5782f0a50ac37b45c4b7e3402bcdded96b4683
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
Toto rozhraní upozorní naslouchací proces (obvykle relace ladění správce [SDM] nebo modul ladění) proces a program vytváření a odstraňování na konkrétním portu. Tyto informace slouží k dispozici v reálném čase zobrazení procesy a programy spuštěné na portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle implementuje toto rozhraní k přijímání oznámení o programu vytváření a likvidace. Modul ladění můžete taky implementovat toto rozhraní tak, aby naslouchala událostem takové port.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Všechny [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní může být dotazován pro <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní. Pak se <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> metodu pro `IDebugPortEvents2` je volána <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní získat <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní. Nakonec <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> metoda v <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní nazývá odesílat události prostřednictvím [událostí](../../../extensibility/debugger/reference/idebugportevents2-event.md) metoda.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metodě `IDebugPortEvents2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Události](../../../extensibility/debugger/reference/idebugportevents2-event.md)|Odesílá události, které popisují vytváření a likvidace procesy a programů na portu.|  
  
## <a name="remarks"></a>Poznámky  
 `IDebugPortEvents2`používá také SDM k ladění programů, které běží v procesu, který je již ladit.  
  
 Port události je předán SDM pomocí tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)