---
title: "Práce v sadě Visual Studio, krok 5, instalace balíčků Python | Microsoft Docs"
description: "Krok 5 základní kurz pro práci s Pythonem v sadě Visual Studio, ukázka funkcích nástroje Visual Studio pro správu balíčků v prostředí Python."
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: bb0890d5f9433e1f73039e4036b884d7bfcb7933
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>Krok 5: Instalace balíčků ve vašem prostředí Python

**Předchozí krok: [spuštění kódu v ladicím programu](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Komunity vývojářů Python má vytvořeného tisíce užitečné balíčky, které můžete začlenit do vašich projektů. Visual Studio poskytuje uživatelské rozhraní ke správě balíčků ve vašich prostředích Python.

1. Vyberte **zobrazení > ostatní okna > prostředí Python** příkazu nabídky. **Prostředí Python** okno otevře jako sdílené do Průzkumníka řešení a ukazuje různých prostředích, která je k dispozici pro vás. Seznam obsahuje obou prostředích, které jste nainstalovali pomocí instalačního programu sady Visual Studio a ty, které můžete nainstalovat samostatně. Prostředí tučným písmem je výchozí prostředí, ve kterém se používá pro nové projekty.

  ![Okno prostředí Python](media/environments-default-view-blue.png)

1. V prostředí **přehled** karta poskytuje rychlý přístup k interaktivních okna pro prostředí spolu s instalační složku a překladače v prostředí. Vyberte například **otevřete okno interaktivní** a v sadě Visual Studio se zobrazí okno aplikace interaktivní pro konkrétní prostředí.

1. Vyberte **balíčky** kartě a zobrazit seznam balíčků, které jsou aktuálně nainstalovány v prostředí.

  ![Balíčky nainstalované v prostředí](media/environments-installed-packages-blue.png)

1. Nainstalujte `matplotlib` zadáním názvu do pole hledání vyberte`pip install`

  ![Instalace matplotlib v prostředí](media/environments-add-matplotlib1.png)

1. Pokud se zobrazí výzva k tomu svůj souhlas pro zvýšení oprávnění.
 
1. Po instalaci balíčku se zobrazí v okně prostředí Python. **X** napravo od balíček odinstaluje ho. 

  ![Dokončení instalace matplotlib v prostředí](media/environments-add-matplotlib2.png)

  Malé indikátor průběhu pod prostředí označuje, že Visual Studio vytváří svou databázi IntelliSense pro nově nainstalovaný balíček. **IntelliSense** kartě také ukazuje podrobnější informace. Všimněte si, že až do dokončení této databáze, IntelliSense funkce, jako jsou automatické doplňování a kontrolu syntaxe nebudou v editoru pro tento balíček aktivní.

1. Vytvoření nového projektu s **soubor > Nový > projekt**, výběrem šablony "Aplikace Python". Do souboru kódu, který se zobrazí vložte následující kód, který vytvoří kosinus wave jako v předchozích krocích kurz pouze v tomto případě vykreslí graficky:

    ```python
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt
    from math import radians

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. Spusťte program s (F5) nebo bez něj (Ctrl + F5), chcete-li zobrazit výstup:

  ![Výstup matplotlib příklad](media/environments-add-matplotlib3.png)

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Práce s úložištěm Git](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

### <a name="going-deeper"></a>Budete hlubší

- [Prostředí Pythonu](managing-python-environments-in-visual-studio.md)
