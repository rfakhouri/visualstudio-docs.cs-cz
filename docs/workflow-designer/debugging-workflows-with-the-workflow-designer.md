---
title: Ladění pracovních postupů pomocí návrháře postupu provádění
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Workflow Designer [WFD], debugging workflows
- Workflow Designer [WFD], debugging workflows
ms.assetid: d71308cf-d464-4536-8711-0d0a8eadb255
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1270e57ae6c9235311569c04ebb982157ea3b608
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949744"
---
# <a name="debug-workflows-with-the-workflow-designer"></a>Ladění pracovních postupů pomocí návrháře postupu provádění

**Návrháře postupu provádění** umožňuje ladění pracovních postupů a vlastní aktivity. Proces a chování jsou podobná výchozí program pro ladění sady Visual Studio.

## <a name="invoke-the-workflow-debugger"></a>Vyvolání ladicího programu pracovních postupů

Obecně platí ladění pracovních postupů stejným způsobem, jako ladíte programy napsané v jiných programovacích jazycích sady Visual Studio. Ladicí program pracovního postupu můžete spustit následujícími způsoby:

- Vyberte **připojit k procesu** na **ladění** nabídky k výběru spuštěného hostitelský proces pro vaši instanci pracovního postupu. Tento postup je stejný jako připojení k procesu hostitele ve spravovaném kódu.

- Stisknutím klávesy **F5** spouštění instance pracovního postupu, nebo aby kontinuálně běžely, jakmile dosáhne zarážky.

- Použití vzdáleného ladění. Informace o použití vzdáleného ladění, naleznete v tématu [jak: Povolení vzdáleného ladění](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).

   > [!NOTE]
   > Pokud se aplikace pracovního postupu, zaměřuje x86 architektury a je hostovaná na počítači se systémem 64bitový operační systém, vzdálené ladění nebudou fungovat, pokud je na vzdáleném počítači nainstalované sady Visual Studio nebo cíl pro aplikace pracovního postupu se změní na  **Jakýkoli procesor**.

## <a name="step-through-code"></a>Krokovat kód

- **Krok v**: Krokování s vnořením do aktivity stisknutím kombinace kláves **F11**. Ladicí program do libovolné obslužné rutiny, která je definována. Pokud není definována žádná obslužná rutina, Krokovat přes aktivity nebo pomocí složených aktivit, které obsahují další aktivity, přejdete na první spouštěné aktivity.

- **Krokovat s Vystoupením:** Krok mimo aktivitu stisknutím kombinace kláves **Shift**+**F11**. Krokování mimo aktivitu spouští aktuální aktivitu a jejich na stejné úrovni aktivity do konce. Ladicí program zastaví se na nadřazený prvek aktuální aktivity. Při procházení z obslužné rutiny kód, ladicí program přeruší na aktivitu, ke kterému je přidružené obslužnou rutinu.

- **Krok přes**: Krok přes aktivitu stisknutím kombinace kláves **F10**. Při krokování přes složené aktivity, ladicí program přeruší na první spustitelný podřízený složené aktivity. Při krokování přes bez složeného, například <xref:System.Activities.Statements.Assign> aktivity, ladicí program provede aktivitu a jeho přidruženými obslužnými rutinami a zalomení na další aktivity. Pokud je aktivita, která se spustí poslední podřízenou aktivitou ve složených aktivit, pak po spuštění, ladicí program přeruší na Nadřazená aktivita.

## <a name="debug-with-f5"></a>Ladění pomocí F5

Pokud vytváříte Konzolová aplikace pracovního postupu, stačí stisknout **F5** pro zahájení ladění do aplikace a pracovního postupu. Pokud vytváříte knihovny aktivit sama o sobě, musíte zadat spustitelný soubor hostitelské aplikace jako spouštěný projekt. Chcete-li nastavit projekt po spuštění **Průzkumníka řešení**, klikněte pravým tlačítkem na název hostitele a vyberte **nastavit jako spouštěný projekt**.