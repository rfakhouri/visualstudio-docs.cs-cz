---
title: Přidání čítačů do sad čítačů pro zatížení testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- counters, counter sets
- counter sets
- load tests, counter sets
ms.assetid: e17d0e71-f982-4fc1-a2df-a1065d37473d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 871ba69d088e58ac1d662f254c72c406c79f86fd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31967882"
---
# <a name="how-to-add-counters-to-counter-sets-using-the-load-test-editor"></a>Postupy: Přidání čítačů do sad čítačů pomocí editoru zátěžových testů

Když vytvoříte zátěžový test pomocí **načíst průvodce testovací**, přidejte počáteční sadu čítačů. Ty nabízejí sadu předdefinovaných sad čítačů pro zátěžové testy. Další informace najdete v tématu [určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

> [!NOTE]
> Pokud jsou zátěžové testy distribuovány napříč vzdálenými počítači, jsou čítače kontroléru a agentů namapovány na sady čítačů kontrolérů a agentů. Další informace o tom, jak používat vzdáleného počítače v zátěžovém testu najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).


 Spravovat vaše čítače v **editoru zátěžových testů**. Sady čítačů, které již byly přidány k testovací jsou viditelné v **nastaví čítač** pracovního zátěžového testu. Jakmile vytvoříte zátěžový test, můžete přidat nové čítače do existujících sad čítačů.

## <a name="to-add-counters-to-a-counter-set"></a>Přidání čítačů do sady čítačů

1.  Otevřete zátěžový test.

2.  Rozbalte **sad čítačů** uzlu. Jsou zobrazeny všechny sady čítačů, které byly přidány do zátěžového testu.

    > [!NOTE]
    > Také obsahuje stromu hierarchie testu zatížení **spustit nastavení** uzlu. Tento uzel obsahuje **čítač nastavit mapování** uzlu, který zobrazuje všechny počítače a sad čítačů, které jsou mapované na těchto počítačích.

3.  Klikněte pravým tlačítkem na existující sadu čítačů a potom zvolte **přidat čítače**.

     **Vyberte čítače výkonu** se zobrazí dialogové okno.

4.  V **počítače** rozevírací pole se seznamem zadejte název počítače pro mapování na. Můžete taky v rozevíracím seznamu vyberte jednu z počítače.

    > [!NOTE]
    > Protože sad čítačů musí být mapován na počítači předtím, než se shromažďují data výkonu, je nutné zadat počítač, na které se mají shromažďovat údaje o výkonu.

5.  Vyberte **kategorie výkonu** vyfiltrujete kategorie dat čítačů výkonu. Zobrazí se dva sloupce dat, ze kterého mají být vyberte čítače výkonu.

    > [!NOTE]
    > Některé kategorie čítače bude vyžadovat také vyberte instanci. Například pokud vyberete čítač SQL, je musíte vybrat instanci systému SQL vzhledem k tomu může být více než jednu instanci SQL nainstalovaný na cílovém počítači.

6.  Vyberte čítač a instanci pro přidání do sady vlastní čítače.

     \- nebo –

     Vyberte **všechny čítače** přepínačů k výběru všechny dostupné čítače.

7.  Zvolte **OK**.

    > [!NOTE]
    > Je také možné přidání čítačů do čítač nastaven vpravo výběr existující čítače nebo kategorie čítače, výběr kopie, a pak vložíte do různých čítač nastavte uzel. Další čítače, které jsou zkopírovány, ale není potřeba, můžete odstranit.

## <a name="see-also"></a>Viz také

- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)