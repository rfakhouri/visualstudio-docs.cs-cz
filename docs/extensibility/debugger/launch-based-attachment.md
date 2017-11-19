---
title: "Na základě spuštění přílohu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2aa9787ad432e402375680c4e27e433236b13249
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Povolení Program chcete ladit](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)