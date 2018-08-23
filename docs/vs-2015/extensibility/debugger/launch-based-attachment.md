---
title: Příloha založená na spuštění | Dokumentace Microsoftu
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
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e52e364e49bb38e6be812edec9f5fa5d8f26df0f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675317"
---
# <a name="launch-based-attachment"></a>Příloha založená na spuštění
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Příloha založená na spuštění](https://docs.microsoft.com/visualstudio/extensibility/debugger/launch-based-attachment).  
  
Příloha založená na spuštění programu je automatické. Při spuštění procesu hostování program podle SDM Příloha založená na spuštění se řídí podobná metoda ručního přílohy cestu. Informace najdete v tématu [připojení k programu](../../extensibility/debugger/attaching-to-the-program.md).  
  
## <a name="the-attaching-process"></a>Proces připojení  
 Hlavní rozdíl je posloupnost událostí po **připojit** volání následujícím způsobem:  
  
1.  Odeslání **IDebugEngineCreateEvent2** objekt SDM události. Podrobnosti najdete v tématu [odesílání událostí](../../extensibility/debugger/sending-events.md).  
  
2.  Volání `IDebugProgram2::GetProgramId` metodu na **IDebugProgram2** předán rozhraní **připojit** metody.  
  
3.  Odeslání **IDebugProgramCreateEvent2** události objektu oznámit SDM, místní **IDebugProgram2** byl vytvořen objekt představující program DE.  
  
4.  Odeslání [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) události objektu oznámit SDM, že se vytvoří nové vlákno pro proces, který spustil.  
  
## <a name="see-also"></a>Viz také  
 [Odesílání požadovaných událostí](../../extensibility/debugger/sending-the-required-events.md)   
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)

