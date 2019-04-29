---
title: Program ovládacího prvku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 6be80904-e66c-4cae-8891-1113b799fb01
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 46e41cacafa2251c96ec7a97899b81034f455d6f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63414215"
---
# <a name="program-control"></a>Řízení programu
V sadě Visual Studio ladění, všechny následující krokování a pokračování rutiny probíhají na úrovni aplikace:

- Nastavení dalšího příkazu, to znamená, že nastavení počítače na další instrukci, který se spustí v konkrétní snímek prostředí

- Provádění, to znamená, že budete pokračovat, ukončete režim krokování

- Krokování na další instrukci

- Pokračujte v aktuálním režimu krokování

- Pozastavení vláken součástí programu

- Obnovování vláken součástí programu

> [!NOTE]
> Zobrazení zásobníku volání se implementuje na úrovni vlákna. Informace o snímcích výčet při zobrazení zásobníku volání pro vlákno, musí implementovat všechny metody [IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md) rozhraní.

## <a name="methods-of-program-control"></a>Metody řízení programu
 V následující tabulce jsou uvedeny metody objektu [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) , který je nutné implementovat pro minimální funkční ladicího stroje (DE) a řízení provádění.

|Metoda|Popis|
|------------|-----------------|
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|Pokračuje ve spuštění všech vláken součástí programu v zastaveném stavu. Vyžaduje se pro řízení provádění.|
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|Pokračuje ve spuštění všech vláken součástí programu v zastaveném stavu. Vyžaduje se pro řízení provádění.|
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|Krok se provádí na dané vlákno. Pokračuje ve spuštění všech vláken součástí programu. Vyžaduje se pro řízení provádění.|

 Pro programy s více vlákny, musíte také implementovat [IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) metoda a všechny metody [IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md) rozhraní.

## <a name="see-also"></a>Viz také:
- [Ovládací prvek a stav zkušební spuštění](../../extensibility/debugger/execution-control-and-state-evaluation.md)