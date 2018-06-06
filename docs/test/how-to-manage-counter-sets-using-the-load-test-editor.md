---
title: Čítač testu zatížení nastaví v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.dialog.countersetmapping
helpviewer_keywords:
- counters, counter sets
- performance counters
- counter sets
- load tests, counter sets
ms.assetid: 64315c2f-a0b2-4378-be16-0774b99beef5
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 27a1cdd3390d6f068947bfcb0daef76eb93fd026
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751985"
---
# <a name="how-to-manage-counter-sets-using-the-load-test-editor"></a>Postupy: Správa sad čítačů pomocí editoru zátěžových testů

Když vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, přidáte počáteční sadu čítačů. Ty nabízejí sadu předdefinovaných sad čítačů pro zátěžové testy.

> [!NOTE]
> Pokud jsou zátěžové testy distribuovány napříč vzdálenými počítači, jsou čítače kontroléru a agentů namapovány na sady čítačů kontrolérů a agentů. Další informace o tom, jak používat vzdáleného počítače v zátěžovém testu najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

Správa sad čítačů zahrnuje výběr sadu počítačů, které chcete shromažďovat údaje o výkonu z a přiřazení sadu sad čítačů ke shromažďování z jednotlivých počítačů. Spravovat vaše čítače v **editoru zátěžových testů**.

![Správa sad čítačů](../test/media/loadtestmanagecountersets.png)

## <a name="to-manage-counter-sets"></a>Správa sad čítačů

1.  Otevřete zátěžový test.

2.  Vyberte **Správa sad čítačů** tlačítko.

     – nebo –

     Klikněte pravým tlačítkem na **sad čítačů** složky v zatížení testování stromu a zvolte **Správa sad čítačů**.

     **Správa sad čítačů** se zobrazí dialogové okno.

3.  (Volitelné) V **vybrané počítače a sad čítačů bude přidán pod následující parametry spuštění** vyberte jiné nastavení spuštění.

    > [!NOTE]
    > To platí jenom Pokud máte více než jedno spuštění nastavení v zátěžovém testu.

4.  (Volitelné) Zvolte **přidat počítač** přidání nové počítače ke sledování. Zobrazí se výzva k zadání názvu. Zadejte název počítače a zobrazí se uzly pod nový záznam. Například **ASP.NET**, **IIS**, **SQL**a další. Zaškrtněte políčka před uzly, které chcete vybrat. Nové čítače se zobrazí v **náhled výběr** podokně.

5.  (Volitelné) V **značek počítače** textového pole, zadejte značky pro přidružení k počítači. Například "TestMachine12 v lab3".

     Značky počítače umožňují identifikovat počítač s názvem snadno rozpoznat.

     Zadané značky jsou zobrazeny v **čítač nastavit mapování** uzel ve stromu v editoru zátěžových testů. Důležitější, značky se zobrazí v sestavách aplikace Excel, které pomáhá identifikovat zúčastněným stranám jakou roli má počítač v zátěžovém testu. Například "Web Server1 v lab2" nebo "Server2 SQL v Phoenix office". Další informace najdete v tématu [Reporting výsledků zátěžových testů pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).

6.  Zvolte **OK**.

## <a name="see-also"></a>Viz také:

- [Kontrolery testů a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)