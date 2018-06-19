---
title: Na základě spuštění přílohu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 892518cc92286f9415e39c96b6ed2afa8eb0d792
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099373"
---
# <a name="launch-based-attachment"></a>Na základě spuštění přílohy
Na základě spuštění přílohy program je automaticky. Při spuštění procesu hostování program podle SDM odpovídá na základě spuštění přílohy podobná metodu ručního přílohy cestu. Informace najdete v tématu [připojení k programu](../../extensibility/debugger/attaching-to-the-program.md).  
  
## <a name="the-attaching-process"></a>Proces připojení  
 Hlavní rozdíl je posloupnost událostí následující **Attach** volat, následujícím způsobem:  
  
1.  Odeslat **IDebugEngineCreateEvent2** událostí objekt, který chcete SDM. Podrobnosti najdete v tématu [odesílání událostí](../../extensibility/debugger/sending-events.md).  
  
2.  Volání `IDebugProgram2::GetProgramId` metodu **IDebugProgram2** předaný rozhraní **Attach** metoda.  
  
3.  Odeslat **IDebugProgramCreateEvent2** objekt události pro upozornění SDM, místní **IDebugProgram2** představující program k DE se objekt vytvořil.  
  
4.  Odeslat [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) objekt události oznámení SDM vytvořený nové vlákno pro proces, který spuštěn.  
  
## <a name="see-also"></a>Viz také  
 [Odesílání požadované událostí](../../extensibility/debugger/sending-the-required-events.md)   
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)