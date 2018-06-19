---
title: Připojení k programu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
ms.assetid: 9a3f5b83-60b5-4ef0-91fe-a432105bd066
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0a4c9719f6258f3bbb5cc8323693001c7f1a9d47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107865"
---
# <a name="attaching-to-the-program"></a>Připojení k programu
Po registraci programy s příslušný port je nutné připojit ladicí program k programu, které chcete k ladění.  
  
## <a name="choosing-how-to-attach"></a>Výběr způsobu připojení  
 Existují tři způsoby, ve kterých pokusí připojit k programu laděné správce ladicí relace (SDM).  
  
1.  Pro programy, které jsou spouštěny modul ladění prostřednictvím [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) získá SDM – metoda (Typická interpretovaný jazyků, např.), [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) rozhraní z [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) objekt přidružený k připojení k programu. Pokud SDM můžete získat `IDebugProgramNodeAttach2` rozhraní SDM pak zavolá [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda. `IDebugProgramNodeAttach2::OnAttach` Metoda vrátí `S_OK` označíte nepřipojili k programu a ostatní pokusy lze připojit k programu.  
  
2.  Pokud SDM můžete získat [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md) rozhraní programu připojovaný ke SDM volání [Attach](../../extensibility/debugger/reference/idebugprogramex2-attach.md) metoda. Tento přístup je typický pro programy, které nebyly spuštěny vzdáleně dodavatel portu.  
  
3.  Pokud program nelze připojit prostřednictvím `IDebugProgramNodeAttach2::OnAttach` nebo `IDebugProgramEx2::Attach` metod SDM načte modul ladění (pokud ještě není zavedený) voláním `CoCreateInstance` funkce a pak zavolá [připojit](../../extensibility/debugger/reference/idebugengine2-attach.md) metoda. Tento přístup je typické pro programy spuštěn místně port dodavatele.  
  
     Je také možné, pro vlastní port dodavatele k volání `IDebugEngine2::Attach` metoda implementace dodavatele vlastní port `IDebugProgramEx2::Attach` metoda. Obvykle v takovém případě dodavatele vlastní port spustí modul ladění ve vzdáleném počítači.  
  
 Přílohy se dosáhne, když správce ladicí relace (SDM) volání [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) metoda.  
  
 Pokud spustíte vaší DE v rámci jednoho procesu jako aplikace, které chcete ladit, pak musí implementovat tyto metody [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md):  
  
-   [Gethostname –](../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md),  
  
-   [GetHostPid](../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)  
  
-   [GetProgramName](../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)  
  
 Po `IDebugEngine2::Attach` metoda je volána, postupujte podle těchto kroků v vaši implementaci `IDebugEngine2::Attach` metoda:  
  
1.  Odeslat [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) událostí objekt, který chcete SDM. Další informace najdete v tématu [odesílání událostí](../../extensibility/debugger/sending-events.md).  
  
2.  Volání [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) metodu [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) objekt, který byl předán `IDebugEngine2::Attach` metoda.  
  
     Tento příkaz vrátí `GUID` používané k identifikaci program. `GUID` Musí být uložen do objektu představuje místní program určený k DE, a je nutné vrácena, pokud `IDebugProgram2::GetProgramId` metoda je volána na `IDebugProgram2` rozhraní.  
  
    > [!NOTE]
    >  Pokud implementujete `IDebugProgramNodeAttach2` rozhraní, program `GUID` je předán `IDebugProgramNodeAttach2::OnAttach` metoda. To `GUID` se používá k programu `GUID` vrácené `IDebugProgram2::GetProgramId` metoda.  
  
3.  Odeslat [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) objekt události pro upozornění SDM, místní `IDebugProgram2` představující program k DE se objekt vytvořil. Podrobnosti najdete v tématu [odesílání událostí](../../extensibility/debugger/sending-events.md).  
  
    > [!NOTE]
    >  Toto není stejná `IDebugProgram2` objekt, který byl předán do `IDebugEngine2::Attach` metoda. Dříve předaný `IDebugProgram2` objekt rozpozná pouze port a je samostatný objekt.  
  
## <a name="see-also"></a>Viz také  
 [Na základě spuštění přílohy](../../extensibility/debugger/launch-based-attachment.md)   
 [Odesílání událostí](../../extensibility/debugger/sending-events.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)   
 [Připojení](../../extensibility/debugger/reference/idebugprogramex2-attach.md)   
 [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md)