---
title: Testování pro jazyk Python částí | Microsoft Docs
description: Nastavení pro kód Python v sadě Visual Studio testování částí pro plně využít výhod funkce Průzkumníka testů, které chcete zjišťovat, spuštění a ladění testy.
ms.custom: ''
ms.date: 07/13/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: eee1ec05a46050c5a994aa2d774a5be0090171f3
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="setting-up-unit-testing-for-python-code"></a>Nastavení pro kód Python testování částí

Testy jednotek jsou části kódu, které testování jiné jednotky kódu v aplikaci, obvykle izolované funkce, třídy a tak dále. Pokud aplikace úspěšně projde všechny jeho testování částí, můžete alespoň důvěřovat správnost jeho nízké úrovně funkčnosti.

Testování částí Python hojně používá k ověření scénáře při navrhování program. Podpora v jazyce Python v sadě Visual Studio obsahuje zjišťování, provádění a ladění testování částí v kontextu vývojových procesech, aniž by museli testy samostatně.

Tento článek poskytuje stručný obrys možnosti testování v sadě Visual Studio s Pythonem částí. Další informace o obecně testování částí v tématu [jednotky Otestujte svůj kód](../test/unit-test-your-code.md).

|   |   |
|---|---|
| ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Testing-Python-hb46k6LWE_405918567) na jednotce testování v Pythonu (2 m 31s). |

## <a name="discovering-and-viewing-tests"></a>Zjišťování a zobrazení testů

Podle konvence, Visual Studio identifikuje testy jako metody, jejichž názvy začínají `test`. Pokud chcete zobrazit toto chování, postupujte takto:

1. Otevřete [projekt Python](managing-python-projects-in-visual-studio.md) načíst v sadě Visual Studio, klikněte pravým tlačítkem na projekt, vyberte **Přidat > novou položku...** , pak vyberte **testování částí Python** následuje **přidat**.

1. Tato akce vytvoří `test1.py` soubor s kódem, který importuje standardní `unittest` modulu, odvozená třída testu z `unittest.TestCase`a vyvolá `unittest.main()` Pokud spustíte skript přímo:

    ```python
    import unittest

    class Test_test1(unittest.TestCase):
        def test_A(self):
            self.fail("Not implemented")

    if __name__ == '__main__':
        unittest.main()
    ```

1. Uložte soubor v případě potřeby a pak otevřete Průzkumníka testů pomocí **testovací > Windows > Průzkumníka testů** příkazu nabídky.

1. Průzkumníka testů hledá projekt pro testy a zobrazí je, jak je uvedeno níže. Dvakrát klikněte na testovací otevře jeho zdrojový soubor.

    ![Testování Explorer zobrazující výchozí test_A](media/unit-test-A.png)

1. Jako další testy přidáte do projektu, můžete uspořádat zobrazení v Průzkumníka testů pomocí skupiny pomocí nabídky na panelu nástrojů:

    ![Testy Explorer Seskupit podle nabídky panelu nástrojů](media/unit-test-group-menu.png)

1. Můžete také zadat text do pole hledání k filtrování testy podle názvu.

Další informace o `unittest` modulu a zápis testů, najdete v článku [Python 2.7 dokumentaci](https://docs.python.org/2/library/unittest.html) nebo [Python 3.4 dokumentaci](https://docs.python.org/3/library/unittest.html) (python.org).

## <a name="running-tests"></a>Spouštění testů

Ve Průzkumníka testů můžete spouštět testy v mnoha různými způsoby:

- **Spustit všechny** jasně spustí všechny testy uvedené (přičemž podléhá filtry).
- **Spustit...**  nabídky poskytuje příkazy ke spuštění se nezdařilo, předaný nebo není spuštění testů jako skupina.
- Můžete vybrat jeden nebo více testů, klikněte pravým tlačítkem a vyberte **spuštění testů vybrané**.

Testy spuštěný na pozadí a otestovat Průzkumníka při dokončování každý test stavu aktualizací:

- Předávání testů zobrazit zelená rick a čas potřebný k spuštění testu:

    ![test_A předán stav](media/unit-test-A-pass.png)

- Neúspěšných testů zobrazit red mezi s **výstup** odkaz, který ukazuje výstup konzoly a `unittest` výstup z testovacím běhu:

    ![Stav test_A se nezdařilo](media/unit-test-A-fail.png)

    ![test_A selhalo s tímto důvodem](media/unit-test-A-fail-reason.png)

## <a name="debugging-tests"></a>Ladění testů

Vzhledem k testování částí jsou části kódu, se vztahují stejně jako jakýkoli jiný kód chyby a někdy je potřeba spustit v ladicí program. V ladicím programu můžete nastavit zarážky, zkontrolujte proměnné a krok prostřednictvím kódu. Diagnostické nástroje sady Visual Studio také poskytuje pro testování částí.

Spuštění ladění, nastavte počáteční zarážku ve vašem kódu, potom klikněte pravým tlačítkem na test (nebo jiný výběr) v Průzkumníku testování a vyberte **ladění vybrané testy**. Visual Studio spustí ladicí program Python, jak by tomu bylo v kódu aplikace.

![Ladění testu](media/unit-test-debugging.png)

Můžete také použít **analýza pokrytí kódu pro vybrané testy** a **profil Test** příkazy, v závislosti na vaší verzi sady Visual Studio (najdete v článku [funkce matice](overview-of-python-tools-for-visual-studio.md#features-matrix)).

### <a name="known-issues"></a>Známé problémy

- Při spouštění, ladění, Visual Studio se zobrazí při spuštění a zastavení, ladění a pak spusťte znovu. Toto chování je očekávané.
- Při ladění několik testů, každé z nich běží nezávisle, který narušuje relaci ladění.
- Visual Studio se občas nepodaří spustit test při ladění. Probíhá pokus o ladění test znovu za normálních okolností úspěšné.
- Při ladění, je možné krok mimo testu do `unittest` implementace. Za normálních okolností další krok se spouští na konec programu a ukončení ladění.
