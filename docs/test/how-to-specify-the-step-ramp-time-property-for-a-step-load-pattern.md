---
title: "Čas doběhu kroku pro vzor zatížení kroku pro zatížení testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, load patterns
ms.assetid: 4a69e857-f93b-4907-9a01-fd1b66291205
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: fdf692057fdd99ee201b38c14454ccd29109d765
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern"></a>Postupy: Nastavení vlastnosti doby doběhu kroku pro vzor zatížení kroku

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností scénáře pro splnění vašich potřeb testování a cíle. Další informace najdete v tématu [návod: vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

**Čas doběhu kroku** je nastavena v okně Vlastnosti. Můžete upravit vlastnosti scénáře zátěžového testu v editoru načíst otestovat.

**Čas doběhu kroku** vlastnost se používá pouze pro vzor zatížení kroku. Další informace najdete v tématu [úpravy vzorů zatížení pro aktivity virtuálního uživatele modelu](../test/edit-load-patterns-to-model-virtual-user-activities.md).

Vzor zatížení kroku slouží ke zvýšení zatížení na serverech, jako zatížení test spustí tak, abyste viděli, jak výkon se liší jako zvyšuje zatížení uživatele. Například pokud chcete zobrazit, jak server nebo servery provést jako uživatel zatížení zvýšení na 2 000 uživatelů, můžete spustit 10 hodin zátěžovém testu s použitím vzor zatížení kroku s následujícími vlastnostmi:

-   Počáteční počet uživatelů: 100

-   Maximální počet uživatelů: 2000

-   Krok trvání (v sekundách): 1 800

-   Krok doběhu doba (v sekundách): 20

-   Počet uživatelů krok: 100

Tato nastavení mají zátěžový test, který je spuštěn na 30 minut (1 800 sekund) při načítání uživatele 100, 200, 300, až 2 000 uživatelů.

> [!NOTE]
> **Čas doběhu kroku** vlastnost je jenom jedna z těchto vlastností, která není k dispozici v nové průvodce zátěžovým testem vyberte.

**Čas doběhu kroku** vlastnost umožňuje být postupná spíše než okamžitou zvýšení z jednoho kroku na další (například ze 100 až 200 uživatelů). V příkladu zatížení uživatele by být zvýšena od 100 na 200 uživatelů po dobu 20 sekundu (zvýšení 5 uživatelů za sekundu).

## <a name="to-edit-the-step-ramp-time-property-for-a-step-load-pattern"></a>Chcete-li upravit vlastnost čas doběhu kroku pro vzor zatížení kroku

1.  Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2.  V zatížení testovat stromy **scénáře** složku, otevřete uzel scénáři chcete určit doběhu kroku čas pro.

3.  Vyberte **vzor zatížení kroku** uzlu.

    > [!NOTE]
    > Vzor zatížení pro tento scénář musí být vzor zatížení kroku. Pokud není, zobrazí vzor zatížení typ zatížení vzor, který je aktuálně přidružena scénáři. Další informace najdete v tématu [úpravy vzorů zatížení pro aktivity virtuálního uživatele modelu](../test/edit-load-patterns-to-model-virtual-user-activities.md).

4.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Tento scénář kategorií a vlastností se zobrazí v okně Vlastnosti.

5.  Nastavit hodnotu pro **čas doběhu kroku** vlastnost tak, že zadáte číslo pro sekund postupně prováděné v každém kroku přidejte uživatele určeného **počet uživatelů krok** vlastnost.

6.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **čas doběhu kroku** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)
- [Úpravy vzorů zatížení pro modelování aktivit virtuálních uživatelů](../test/edit-load-patterns-to-model-virtual-user-activities.md)