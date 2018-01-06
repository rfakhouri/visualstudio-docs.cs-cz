---
title: IDebugProgramCreateEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramCreateEvent2
helpviewer_keywords: IDebugProgramCreateEvent2 interface
ms.assetid: b19a7934-6179-4a68-9075-bd7dcd640b05
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d2bffb1a4a884fe0e6601a6056273e9679a3e6cd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramcreateevent2"></a>IDebugProgramCreateEvent2
Toto rozhraní zasílá modul ladění (DE) zadaný pro relaci ladění správce (SDM) po připojení k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní informuje, že program vytvořila, obvykle v době, kdy program je připojen k implementuje DE nebo dodavatele vlastní port. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM `QueryInterface` metody přístup `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE nebo dodavatele vlastní port vytvoří a odešle tento objekt události tak, aby odesílaly vytvoření programu. DE odešle tato událost pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při jej připojit k programu laděné. Vlastní port dodavatele odešle tato událost pomocí [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) rozhraní.  
  
## <a name="remarks"></a>Poznámky  
 DE nebo vlastní port dodavatele publikuje novou [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní voláním [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)