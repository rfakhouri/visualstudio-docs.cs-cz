---
title: Příloha založená na spuštění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 09a6b39bef9ba6af098bf92d779a490e22492209
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60044847"
---
# <a name="launch-based-attachment"></a>Příloha založená na spuštění
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Příloha založená na spuštění programu je automatické. Při spuštění procesu hostování program podle SDM Příloha založená na spuštění se řídí podobná metoda ručního přílohy cestu. Informace najdete v tématu [připojení k programu](../../extensibility/debugger/attaching-to-the-program.md).  
  
## <a name="the-attaching-process"></a>Proces připojení  
 Hlavní rozdíl je posloupnost událostí po **připojit** volání následujícím způsobem:  
  
1. Odeslání **IDebugEngineCreateEvent2** objekt SDM události. Podrobnosti najdete v tématu [odesílání událostí](../../extensibility/debugger/sending-events.md).  
  
2. Volání `IDebugProgram2::GetProgramId` metodu na **IDebugProgram2** předán rozhraní **připojit** metody.  
  
3. Odeslání **IDebugProgramCreateEvent2** události objektu oznámit SDM, místní **IDebugProgram2** byl vytvořen objekt představující program DE.  
  
4. Odeslání [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) události objektu oznámit SDM, že se vytvoří nové vlákno pro proces, který spustil.  
  
## <a name="see-also"></a>Viz také  
 [Odesílání požadovaných událostí](../../extensibility/debugger/sending-the-required-events.md)   
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)
