---
title: Práce s kurzu Python krok 5 instalace balíčků
description: Krok 5 návod základní možnosti Python v sadě Visual Studio, ukázka funkcích nástroje Visual Studio pro správu balíčků v prostředí Python.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d67ec84271534de84de588cd29376e2cdb437294
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37055978"
---
# <a name="step-5-install-packages-in-your-python-environment"></a>Krok 5: Instalace balíčků ve vašem prostředí Python

**Předchozí krok: [spuštění kódu v ladicím programu](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Komunity vývojářů Python má vytvořeného tisíce užitečné balíčky, které můžete začlenit do vašich projektů. Visual Studio poskytuje uživatelské rozhraní ke správě balíčků ve vašich prostředích Python.

1. Vyberte **zobrazení > ostatní okna > prostředí Python** příkazu nabídky. **Prostředí Python** okno otevře jako sdílené do Průzkumníka řešení a ukazuje různých prostředích, která je k dispozici pro vás. Seznam obsahuje obou prostředích, které jste nainstalovali pomocí instalačního programu sady Visual Studio a ty, které můžete nainstalovat samostatně. Prostředí tučným písmem je výchozí prostředí, ve kterém se používá pro nové projekty.

  ![Okno prostředí Python](media/environments-default-view-blue.png)

1. V prostředí **přehled** karta poskytuje rychlý přístup k interaktivních okna pro prostředí spolu s instalační složku a překladače v prostředí. Vyberte například **otevřete okno interaktivní** a v sadě Visual Studio se zobrazí okno aplikace interaktivní pro konkrétní prostředí.

1. Vyberte **balíčky** kartě a zobrazit seznam balíčků, které jsou aktuálně nainstalovány v prostředí.

  ![Balíčky nainstalované v prostředí](media/environments-installed-packages-blue.png)

1. Nainstalujte `matplotlib` zadáním názvu do pole hledání vyberte `pip install`

  ![Instalace matplotlib v prostředí](media/environments-add-matplotlib1.png)

1. Pokud se zobrazí výzva k tomu svůj souhlas pro zvýšení oprávnění.

1. Po instalaci balíčku se zobrazí v okně prostředí Python. **X** napravo od balíček odinstaluje ho.

  ![Dokončení instalace matplotlib v prostředí](media/environments-add-matplotlib2.png)

  Indikátor průběhu malé se mohou objevit pod prostředí k označení, že Visual Studio vytváří svou databázi IntelliSense pro nově nainstalovaný balíček. **IntelliSense** kartě také ukazuje podrobnější informace. Všimněte si, že až do dokončení této databáze, IntelliSense funkce, jako jsou automatické doplňování a kontrolu syntaxe nebudou v editoru pro tento balíček aktivní.

  Všimněte si, že **Visual Studio 2017 verze 15,6 operací** a později používá jiné a rychlejší metody pro práci s IntelliSense a zobrazí zprávu za tímto účelem on **IntelliSense** kartě.

1. Vytvoření nového projektu s **soubor > Nový > projekt**, výběrem šablony "Aplikace Python". Do souboru kódu, který se zobrazí vložte následující kód, který vytvoří kosinus wave jako v předchozích krocích kurz pouze v tomto případě vykreslí graficky:

    ```python
    from math import radians
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. Spusťte program s (F5) nebo bez něj (Ctrl + F5), chcete-li zobrazit výstup:

  ![Výstup matplotlib příklad](media/environments-add-matplotlib3.png)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Práce s úložištěm Git](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

### <a name="go-deeper"></a>Přejděte hlubší

- [Prostředí Pythonu](managing-python-environments-in-visual-studio.md)
