---
title: "IPython REPL v sadě Visual Studio | Microsoft Docs"
description: "Použití interaktivních okna Visual Studio v režimu IPython pro uživatelsky přívětivý interaktivní vývojové prostředí s funkcemi interaktivní paralelní výpočty."
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: d084731c821bf31743e8c4dce5f31881f19a56f4
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="using-ipython-in-the-interactive-window"></a>V okně interaktivní pomocí IPython

Okno interaktivní sady Visual Studio v režimu IPython je pokročilé prostředí ještě uživatelsky přívětivý interaktivní vývoj, které má funkce interaktivní paralelní výpočty. Toto téma vás provede pomocí IPython v sadě Visual Studio interaktivní okna, ve kterém jsou všechny normálního [interaktivních okna](python-interactive-repl-in-visual-studio.md) funkce jsou také k dispozici.

Pro účely tohoto postupu byste měli mít [Anaconda](https://www.continuum.io) prostředí nainstalovaná, která zahrnuje IPython a potřebné knihovny.

> [!Note]
> IronPython nepodporuje IPython, přestože, které můžete vybrat ve formuláři interaktivní možnosti. Další informace najdete v článku [žádost o funkce](https://github.com/Microsoft/PTVS/issues/84).

1. Otevřete Visual Studio, přepněte do okna prostředí Python (**zobrazení > ostatní okna > prostředí Python**) a vyberte prostředí Python, které se zobrazily při spuštění IPython.

1. Podívejte se na **balíčky** (nebo **pip**) kartě a ujistěte se, že `IPython` a `matplotlib` jsou uvedeny. Pokud tomu tak není, nainstalujte je zde.

1. Vyberte **přehled** a vyberte **použití IPython interaktivním režimu.** (V sadě Visual Studio 2015, vyberte **konfigurovat interaktivní možnosti** otevřete **možnosti** dialogové okno, nastavte **interaktivním režimu** IPython a vyberte **OK** ).

1. Vyberte **otevřete okno interaktivní** se zprovoznit interaktivních okna v režimu IPython. Budete muset resetovat okno, pokud jste změnili právě interaktivním režimu; Možná budete také muset stiskněte klávesu Enter, pokud je to pouze >>> se zobrazí dotaz.

    ![Interaktivní okno v režimu IPython](media/ipython-repl-03.png)

1. Zadejte následující kód:

  ```python
  x = linspace(0, 5, 10)
  y = x ** 2
  plot(x, y, 'r', x, x ** 3, 'g', x, x ** 4, 'b')
  ```

1. Po zadání poslední řádek, měli byste vidět vložené grafu (které velikost můžete změnit tak, že přetáhnete v pravém dolním) v případě potřeby.

    ![Vložené grafu v okně interaktivní](media/ipython-repl-04.png)

1. Místo zadání do REPL, můžete místo toho napsat kód v editoru, vyberte ho, klikněte pravým tlačítkem a vyberte **odeslat do interaktivní** příkazu (nebo stiskněte klávesu Ctrl-zadejte). Vyzkoušejte si vložením kódu níže do nového souboru v editoru její Ctrl-A potom odesílání do okna interaktivní výběr. (Všimněte si, že Visual Studio odešle kód jako jednu jednotku, aby se zabránilo budete zprostředkující nebo jeho část grafy. Všimněte si, že pokud nemáte otevřete pomocí různých prostředí vybrané projekt Python, Visual Studio otevře interaktivních okna pro libovolnou prostředí je vybraná jako výchozí v **prostředí Python** okno.)

    ```python
    from mpl_toolkits.mplot3d import Axes3D
    import matplotlib.pyplot as plt
    import numpy as np
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')
    for c, z in zip(['r', 'g', 'b', 'y'], [30, 20, 10, 0]):
        xs = np.arange(20)
        ys = np.random.rand(20)
        # You can provide either a single color or an array. To demonstrate this,
        # the first bar of each set is colored cyan.
        cs = [c] * len(xs)
        cs[0] = 'c'
        ax.bar(xs, ys, zs=z, zdir='y', color=cs, alpha=0.8)

    ax.set_xlabel('X')
    ax.set_ylabel('Y')
    ax.set_zlabel('Z')
    plt.show()
    ```

    ![Odesílání kódu z editoru do interaktivních okna](media/ipython-repl-05.png)

1. Pokud chcete zobrazit grafy mimo okno interaktivní, spusťte kód místo pomocí **ladění > Spustit bez ladění** příkaz.

IPython obsahuje mnoho dalších užitečné funkcí například uvozovací znaky prostředí systému a nahrazení proměnné, zaznamenávání výstup atd. Odkazovat [IPython dokumentace](http://ipython.org/documentation.html) Další informace.

## <a name="related-topics"></a>Související témata

- Chcete-li použít Jupyter snadno a bez instalace, zkuste bezplatnou [poznámkových bloků Azure hostovaná služba](https://notebooks.azure.com/) které vám umožní zachovat a sdílet s ostatními poznámkové bloky.

- Jupyter (dříve označované jako IPython) můžete také spustit na virtuálním počítači v Azure vlastní systému Windows nebo Linux. Podrobnosti najdete v tématu [vytvoření Azure virtuální počítač. instalace Jupyter a systémem Azure Poznámkový blok Jupyter](/azure/virtual-machines/virtual-machines-linux-jupyter-notebook).
