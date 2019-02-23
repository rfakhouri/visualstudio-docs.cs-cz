---
title: Příloha založená na spuštění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4a967b48f7c904ecc22d0b3ea077ae5cecd2625
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718960"
---
# <a name="launch-based-attachment"></a>Příloha založená na spuštění
Příloha založená na spuštění programu je automatické. Při spuštění procesu hostování program podle SDM Příloha založená na spuštění se řídí podobná metoda ručního přílohy cestu. Informace najdete v tématu [připojit k programu](../../extensibility/debugger/attaching-to-the-program.md).

## <a name="the-attaching-process"></a>Proces připojení
 Hlavní rozdíl je posloupnost událostí po **připojit** volání následujícím způsobem:

1.  Odeslání **IDebugEngineCreateEvent2** objekt SDM události. Podrobnosti najdete v tématu [odesílání událostí](../../extensibility/debugger/sending-events.md).

2.  Volání `IDebugProgram2::GetProgramId` metodu na **IDebugProgram2** předán rozhraní **připojit** metody.

3.  Odeslání **IDebugProgramCreateEvent2** události objektu oznámit SDM, místní **IDebugProgram2** byl vytvořen objekt představující program DE.

4.  Odeslání [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) události objektu oznámit SDM, že se vytvoří nové vlákno pro proces, který spustil.

## <a name="see-also"></a>Viz také:
- [Odesílání požadovaných událostí](../../extensibility/debugger/sending-the-required-events.md)
- [Povolit program k ladění](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)