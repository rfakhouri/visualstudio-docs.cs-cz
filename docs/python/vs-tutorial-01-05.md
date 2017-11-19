---
title: "Práce s Python v sadě Visual Studio, krok 5 | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 69e51c46-9a10-4d6f-9f74-2d1385beb1ac
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 30f89023d09ab90cae2698de976eaef44165b0fb
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>Krok 5: Instalace balíčků ve vašem prostředí Python

**Předchozí krok: [spuštění kódu v ladicím programu](vs-tutorial-01-04.md)**

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
> [Práce s Gitem](vs-tutorial-01-06.md)

### <a name="going-deeper"></a>Budete hlubší
- [Prostředí Python](python-environments.md)
