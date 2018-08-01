---
title: Shromažďování veškerých podrobností pro virtuálních uživatelů pro zátěžové testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, virtual user activity chart, configuring
- virtual user activity chart, configuring
ms.assetid: cb22e43b-af4d-4e09-9389-3c3fa00786f7
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 70930a09f01450d59b44678ebd26d7e742af7294
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379622"
---
# <a name="how-to-configure-load-tests-to-collect-full-details-to-enable-virtual-user-activity-in-test-results"></a>Postupy: Konfigurace testů pro shromažďování veškerých podrobností a zpřístupnění aktivity virtuálních uživatelů ve výsledcích testu zatížení

Použít **graf aktivity virtuálního uživatele** pro zátěžový test, je nutné nakonfigurovat zátěžového testu pro shromažďování veškerých podrobností. Při konfiguraci zátěžového testu, chcete-li to provést, vyberte **detaily o všech jednotlivých položkách** nastavení **úložiště podrobností časování** vlastností spojených se zátěžovým testem. V tomto režimu bude zátěžový test shromažďovat podrobné informace o každém testu, stránce a transakci.

 Pokud provádíte aktualizaci projektu z předchozí verze zátěžového testu sady Visual Studio, sběr všech podrobností povolíte podle následujících kroků.

 **Detaily o všech jednotlivých položkách** nastavení **úložiště podrobností časování** vlastnost lze nastavit na kteroukoli z následujících možností:

-   **Detaily o všech jednotlivých položkách:** shromažďuje a ukládá data jednotlivých časování pro každý test, transakci a stránku zmíněnou v průběhu testu.

    > [!NOTE]
    > **Detaily o všech jednotlivých položkách** musí být vybrána možnost povolit informace o datech virtuálních uživatelů ve vašich výsledcích zátěžového testu.

-   **Žádné:** neshromažďuje žádné podrobnosti jednotlivých časování. Průměrné hodnoty jsou však stále k dispozici.

-   **Pouze statistiky:** ukládá jednotlivá data časování, ale pouze jako percentil. Tím ušetříte prostředky prostoru.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>Konfigurace vlastnosti úložiště podrobností načasování v zátěžovém testu

1.  Otevřete zátěžový test v **editoru zátěžového testu**.

2.  Rozbalte **parametrů běhu** uzlu v zátěžovém testu.

3.  Zvolte v běhu, které chcete konfigurovat, například **běhu1 [aktivní]**.

4.  Otevřít **vlastnosti** okna. Na **zobrazení** nabídce vyberte možnost **okno vlastností**.

5.  V části **výsledky** kategorie, zvolte **úložiště podrobností časování** vlastnosti a vyberte **detaily o všech jednotlivých položkách**.

     Po nakonfigurování **detaily o všech jednotlivých položkách** nastavení **úložiště podrobností časování** vlastností, můžete spustit zatížení testování a zobrazení **graf aktivity virtuálního uživatele**. Další informace najdete v tématu [postupy: analýza, co dělají virtuálních uživatelů během zátěžového testu](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md).

## <a name="see-also"></a>Viz také:

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)