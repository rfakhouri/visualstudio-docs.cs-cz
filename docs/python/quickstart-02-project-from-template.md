---
title: "Rychlý úvod: Vytvořte projekt Python ze šablony v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: ee329df0bda8869215969941024deba6d94743fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>Rychlý úvod: Vytvořte projekt Python ze šablony v sadě Visual Studio

Jakmile jste [nainstalována podpora v jazyce Python ve Visual Studio 2017](installation.md), je snadné vytvořit nový projekt Python pomocí různých šablon.

1. Spusťte sadu Visual Studio.

1. Vyberte **soubor > Nový > projekt** (Ctrl + Shift + N). V **nový projekt** dialogové okno, vyhledejte "Python" a vyberte požadované šablony. Všimněte si, že výběrem šablony zobrazuje krátký popis co Šablona nabízí. (Viz také [projektů v jazyce Python](python-projects.md#project-templates).)

    ![Dialogové okno Nový projekt VS2017 pomocí šablony Python](media/projects-new-project-dialog2.png)

1. Pro tento rychlý start, vyberte šablonu, "Python aplikace", poskytnout projektu umístění a název (například "MakePI") a vyberte **OK**. 

1. Visual Studio vytvoří soubor projektu ( `.pyproj` soubor na disku) společně s dalšími soubory podle šablony. Projekt se šablonou "Python aplikace", obsahuje pouze jeden prázdný soubor se stejným názvem jako projektu. Soubor je otevřen v editoru Visual Studio ve výchozím nastavení.

    ![Výsledný projektu při použití šablony aplikace Python](media/projects-new-structure.png)

1. Přidáte kód soubor otevřít, například kód níže, vypočítá a zobrazí 1000 číslic čísla pí:

    ```python
    """ Print digits of PI; code adapted from the second, shorter solution
    at http://www.codecodex.com/wiki/Calculate_digits_of_pi#Python
    """

    from time import perf_counter

    def pi_digits_Python(digits):
        scale = 10000
        maxarr = int((digits / 4) * 14)
        arrinit = 2000
        carry = 0
        arr = [arrinit] * (maxarr + 1)
        output = ""

        for i in range(maxarr, 1, -14):
            total = 0
            for j in range(i, 0, -1):
                total = (total * j) + (scale * arr[j])
                arr[j] = total % ((j * 2) - 1)
                total = total / ((j * 2) - 1)

            output += "%04d" % (carry + (total / scale))
            carry = total % scale

        return output;

    def test_py():
        digits = 1000;

        start = perf_counter()
        output = pi_digits_Python(digits);
        elapsed = perf_counter() - start;

        print("PI to " + str(digits) + " digits in " + str(int(elapsed * 10000)/10000) + " seconds:")

        ## replace inserts the decimal point
        print(output.replace("3", "3.", 1))

    if __name__ == "__main__":
        test_py();
    ```

1. Spusťte program stisknutím Ctrl + F5 nebo výběrem **ladění > Spustit bez ladění** v nabídce. Výsledky jsou zobrazeny v okně konzoly.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](vs-tutorial-01-01.md)

## <a name="see-also"></a>Viz také

- [Vytvoření prostředí pro existující překladač Pythonu](python-environments.md#creating-an-environment-for-an-existing-interpreter).
- [Instalace podpory Python v sadě Visual Studio 2015 a starší](installation.md).
- [Umístění instalace](installation.md#install-locations).
