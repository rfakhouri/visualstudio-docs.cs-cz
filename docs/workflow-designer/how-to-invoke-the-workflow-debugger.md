---
title: "Postupy: volání ladicí program pracovního postupu | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 34c592af-f4f6-4d02-99f6-63a94698e48b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b84fad1bd0daf1f7163a06683f8c41ff0257a2e4
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-invoke-the-workflow-debugger"></a>Postupy: volání ladicí program pracovního postupu
Obecně platí při ladění pracovních postupů, stejně jako při ladění programy vytvořené v jiné sadě Visual Studio programovací jazyky. Ladicí program pracovního postupu můžete spustit těmito způsoby:

-   Vyberte **připojit k procesu** na **ladění** nabídce vyberte běžící proces hostitele pro instanci pracovního postupu. Tento postup je stejný jako připojování k hostitelskému procesu ve spravovaném kódu.

-   Stiskněte klávesu **F5** spustit instance pracovního postupu nebo chcete-li pokračovat, aby po zarážku narazil spustila.

-   Použití vzdálené ladění. Informace o používání vzdálené ladění najdete v tématu [postupy: povolení vzdáleného ladění](http://go.microsoft.com/fwlink/?LinkId=196257).

    > [!NOTE]
    > Pokud je pracovní postup aplikace určena x86 architektura a je hostovaná na počítači se systémem 64bitový operační systém, pak vzdálené ladění nebude fungovat, pokud [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] je nainstalován na vzdáleném počítači nebo cíl pro pracovní postup aplikace se změní na **Žádné procesoru**.

### <a name="stepping-through-code"></a>Procházení kódu

-   **Krok v**: můžete krok do aktivity pomocí **F11**. Ladicí program do jakékoli obslužná rutina, která je definována. Pokud je definována žádná obslužná rutina, krok přes aktivity nebo složený aktivitami, které obsahují další aktivity, krok do první provádění aktivity.

-   **Krok na více systémů:** můžete krok mimo aktivity pomocí **Shift F11**. Krokování s mimo aktivitu spouští aktuální aktivita a její na stejné úrovni aktivity dokončen. Ladicí program pak dělí na nadřazené aktuální aktivity. Když zanoříte z obslužnou rutinu kódu, ladicího programu dělí na aktivitu, ke kterému je přiřazeno obslužná rutina.

-   **Krokovat s přeskočením**: můžete krok přes aktivity pomocí **F10**. Když krokování přes složených aktivit, ladicího programu dělí na prvním podřízeným objektem spustitelné složené aktivity. Když krokování přes jiný složené, například <xref:System.Activities.Statements.Assign> aktivity, ladicí program spustí aktivita a její přidružené obslužné rutiny a zalomení na další aktivitu. Pokud aktivita, která se spustí poslední podřízené aktivity ve složených aktivit, pak po spuštění, ladicího programu dělí na nadřazené aktivity.

### <a name="debugging-with-f5"></a>Ladění pomocí F5

-   Pokud jsou sestavení projektu konzolové aplikace pracovního postupu, jednoduše stiskněte **F5** zahájíte ladění do své aplikace a pracovní postup. Pokud vytváříte knihovna aktivit svoje vlastní, musí mít aplikace spustitelný soubor hostitele jako spouštěný projekt. Chcete-li nastavit spouštěný projekt **Průzkumníku řešení**, klikněte pravým tlačítkem na název projektu hostitele a vyberte **nastavit jako spouštěný projekt**.

## <a name="see-also"></a>Viz také

- [Postupy: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [Ladění pracovních postupů pomocí návrháře postupu provádění](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)