---
title: "Shromažďování veškerých podrobností pro virtuálních uživatelů, pro zatížení testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, virtual user activity chart, configuring
- virtual user activity chart, configuring
ms.assetid: cb22e43b-af4d-4e09-9389-3c3fa00786f7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b410c91ff2b6c57b86c7fe377df4bf31173f9384
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-configure-load-tests-to-collect-full-details-to-enable-virtual-user-activity-in-test-results"></a>Postupy: Nastavení zátěžových testů pro shromažďování veškerých podrobností a zpřístupnění aktivity virtuálních uživatelů ve výsledcích testu

Chcete-li použít graf aktivity virtuálního uživatele pro zátěžový test, je nutné zátěžový test nakonfigurovat, aby shromažďoval všechny podrobnosti. Pro konfiguraci zátěžový test, chcete-li to provést, vyberte **všech podrobností o jednotlivých** nastavení **úložiště podrobností časování** vlastnost spojená s zátěžový test. V tomto režimu bude zátěžový test shromažďovat podrobné informace o každém testu, stránce a transakci.

 Pokud provádíte aktualizaci projektu z předchozí verze zátěžového testu sady Visual Studio, sběr všech podrobností povolíte podle následujících kroků.

 **Všech podrobností o jednotlivých** nastavení **úložiště podrobností časování** může být nastavena na žádnou z následujících možností:

-   **Všechny podrobnosti o jednotlivých:** shromažďuje a ukládá data jednotlivých časování pro každý test, transakce a stránka vydané během testu.

    > [!NOTE]
    > **Všech podrobností o jednotlivých** je třeba vybrat možnost povolení informace data virtuálních uživatelů v si výsledky testu zatížení.

-   **Žádné:** neshromažďuje žádné informace o jednotlivých časování. Průměrné hodnoty jsou však stále k dispozici.

-   **Pouze statistiku:** ukládá data jednotlivých časování, ale pouze jako percentilu data. To umožňuje ušetřit místo na prostředky.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>Konfigurovat vlastnosti úložiště podrobností časování v zátěžovém testu

1.  Otevřete v editoru zátěžových testů zátěžový test.

2.  Rozbalte **spustit nastavení** uzlu v zátěžovém testu.

3.  Zvolit na spuštění nastavení, které chcete konfigurovat, například **spustit Settings1 [Active]**.

4.  Otevřete okno Vlastnosti. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

5.  V části **výsledky** kategorie, vyberte **úložiště podrobností časování** vlastnost a vyberte **všech podrobností o jednotlivých**.

     Po dokončení konfigurace **všech podrobností o jednotlivých** nastavení **úložiště podrobností časování** vlastnost, můžete spustit zátěžový test a zobrazení grafu aktivity virtuálního uživatele. Další informace najdete v tématu [postupy: Analýza co virtuální uživatelé jsou to během zátěžový Test](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md).

## <a name="see-also"></a>Viz také

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)