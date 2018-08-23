---
title: Připojení a odpojení programu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a7129fab85d405d941394c02abf79ba29e787f5b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633240"
---
# <a name="attaching-and-detaching-to-a-program"></a>Připojení a odpojení programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [připojení a odpojení programu](https://docs.microsoft.com/visualstudio/extensibility/debugger/attaching-and-detaching-to-a-program).  
  
Připojování ladicího programu vyžaduje odeslání tak správné pořadí metod a událostí pomocí vlastních atributech.  
  
## <a name="sequence-of-methods-and-events"></a>Posloupnost metody a události  
  
1.  Správce ladění relace (SDM) volá [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metody.  
  
     Na základě modelu procesu ladicí stroj (DE), `IDebugProgramNodeAttach2::OnAttach` metoda vrátí jednu z následujících metod, které určuje, co bude dál.  
  
     Pokud `S_FALSE` se vrátí ladicí stroj úspěšně připojí k programu. V opačném případě [připojit](../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána k dokončení procesu připojování.  
  
     Pokud `S_OK` se vrátí, DE je třeba načíst ve stejném procesu jako SDM. SDM provádí následující úlohy:  
  
    1.  Volání [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) získat informace pro modul DE.  
  
    2.  Společně vytvoří DE.  
  
    3.  Volání [připojit](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
2.  Odešle DE [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
3.  Odešle DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) k SDM s `EVENT_SYNC` atribut.  
  
4.  Odešle DE [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) k SDM s `EVENT_SYNC_STOP` atribut.  
  
 Odpojení od programu je jednoduché, dvoustupňový proces, následujícím způsobem:  
  
1.  Volání SDM [odpojit](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
2.  Odešle DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)

