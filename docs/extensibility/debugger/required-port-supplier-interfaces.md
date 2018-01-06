---
title: "Požadovaná rozhraní dodavatele Port | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ab243886341d720045fc2d1fbd7a813b7d81c9e5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="required-port-supplier-interfaces"></a>Požadovaný Port dodavatele rozhraní
Port dodavatele musí implementovat [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní.[ IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 Vzhledem k tomu, že port dodavatele poskytuje porty, musí je také implementovat. Proto se musí implementovat rozhraní následující:  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     Popisuje, port a můžete vytvořit výčet všech procesů spuštěných na tomto portu.  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     Poskytuje pro spuštění a ukončení procesů na portu.  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     Poskytuje mechanismus pro aplikace běžící v rámci kontextu tento port k upozornění na program uzlu vytváření a likvidace. Další informace najdete v tématu [Program uzly](../../extensibility/debugger/program-nodes.md).  
  
-   `IConnectionPointContainer`  
  
     Poskytuje bod připojení pro [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md).  
  
## <a name="port-supplier-operation"></a>Operace dodavatele portu  
 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) podřízený obdrží oznámení, když proces a programy jsou vytvořen a zničen na portu. Port je potřeba poslat [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) vytvoření procesu a [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) při procesu zničen na portu. Port je také potřeba odesílat [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) vytvoření programu a [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) při program zničen v procesu spuštěného na tomto portu.  
  
 Port obvykle zasílá program vytvořit a zrušení události v reakci [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) a [RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) metody, v uvedeném pořadí.  
  
 Protože port se můžou spouštět a ukončit procesy fyzické a logické programy, musí tato rozhraní taky implementovat pomocí modulu ladění:  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     Popisuje proces fyzické. Minimálně musí být implementována následujících metod:  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName –](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [Getprocessid –](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     Poskytuje způsob, jak SDM k připojení a odpojení sám sebe z procesu.  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     Popisuje logické program. Minimálně musí být implementována následujících metod:  
  
    -   [GetName –](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [Getprocess –](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     Poskytuje způsob, jak SDM připojit k tomuto programu.  
  
## <a name="see-also"></a>Viz také  
 [Implementace dodavatele portu](../../extensibility/debugger/implementing-a-port-supplier.md)