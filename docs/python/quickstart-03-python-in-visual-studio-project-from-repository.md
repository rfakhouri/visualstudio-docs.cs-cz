---
title: Rychlý start - klonování úložiště Python kódu
description: V tento rychlý start vytvořte projekt Python v sadě Visual Studio klonováním Python koans úložiště pomocí sady Visual Studio Team Explorer.
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 24cc9b114d004c7a70442cf88e48b4bd5d59823a
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="quickstart-clone-a-repository-of-python-code-in-visual-studio"></a>Rychlý úvod: klonovat úložiště Python kódu v sadě Visual Studio

Jakmile jste [nainstalována podpora v jazyce Python ve Visual Studio 2017](installing-python-support-in-visual-studio.md), můžete snadno klonovat úložiště v kódu jazyka Python a vytvořte projekt z něj.

[!INCLUDE[install-github-extension](includes/install-github-extension.md)]

2. Spusťte sadu Visual Studio.

3. Vyberte **zobrazení > Team Explorer** otevřete **Team Explorer** okno, ve kterém můžete připojit k webu GitHub nebo Visual Studio Team Services, nebo klonovat úložiště. (Pokud se nezobrazí **připojit** stránky uvedená níže, vyberte ikonu moduly na horním panelu nástrojů, které přejdete na této stránce.)

    ![Team explorer okno zobrazující Visual Studio Team Services, GitHub a klonování úložiště](media/team-explorer.png)

4. V části **místní úložiště Git**, vyberte **klon** příkaz a potom zadejte `https://github.com/gregmalcolm/python_koans` v poli Adresa URL zadejte složku pro klonovaný soubory a vyberte **klon** tlačítko.

    > [!Tip]
    > Složky, kterou zadáte v Team Explorer je přesný složka přijímat klonovaný soubory. Na rozdíl od `git clone` příkazu vytvoříte klon v Team Exploreru nevytvoří automaticky podsložku s názvem úložiště.

5. Po dokončení klonování se zobrazí název úložiště v **místní úložiště Git** seznamu. Dvakrát klikněte na tento název přejděte na řídicím panelu úložiště v **Team Explorer**.

6. V části **řešení**, vyberte **nový**.

    ![Okno Průzkumníka týmu, vytvoření nového projektu z klonu](media/team-explorer-new-project.png)

7. V **nový projekt** dialog, který se zobrazí, přejděte na jazyk Python (nebo vyhledávání v "Python"), vyberte "Z existující kód Python", zadejte název projektu, nastavte **umístění** do stejné složky jako úložiště a vyberte **OK**. V průvodci, který se zobrazí, vyberte **Dokončit**.

8. Vyberte **zobrazení > Průzkumníku řešení** z nabídky.

9. V **Průzkumníku řešení**, rozbalte `python3` uzel, klikněte pravým tlačítkem na `contemplate_koans.py`a vyberte **nastavit jako spouštěcí soubor**. Tento krok informuje soubor, který se má používat při spuštění projektu sady Visual Studio.

10. Vyberte **Projekt > Vlastnosti Koans** v nabídce vyberte **Obecné** kartě a nastavte **pracovní adresář** na "python3". Tento krok je nezbytný, protože ve výchozím nastavení sady Visual Studio nastavuje pracovní adresář na kořenu projektu a nikoli umístění souboru spuštění (`python3\contemplate_koans.py`, který se zobrazí ve vlastnostech projektu). Kód programu hledá soubor `koans.txt` pracovní složku, takže bez změnou této hodnoty se zobrazuje chyba za běhu.

    ![Nastavení pracovní adresář pro projekt Python](media/projects-set-working-directory.png)

11. Stiskněte klávesy Ctrl + F5 nebo vyberte **ladění > Spustit bez ladění** ke spuštění programu. Pokud se zobrazí `FileNotFoundError` pro `koans.txt`, zkontrolujte pracovní adresář nastavení popsané v předchozím kroku.

12. Když se program spouští úspěšně, zobrazí chybu kontrolní výraz na řádku 17 `python3/koans/about_asserts.py`. To je úmyslné: program navrženy tak, aby Python tak, že jste opravte všechny chyby záměrné. (Další informace najdete na [Ruby Koans](http://rubykoans.com/), které daly podnět Python Koans.)

    ![První výstup z programu koans Python](media/koans-output.png)

13. Otevřete `python3/koans/about_asserts.py` tak, že přejdete k němu v Průzkumníku řešení a dvojitým kliknutím na soubor. Všimněte si, že čísla řádků se nezobrazí ve výchozím nastavení v editoru. Chcete-li toto nastavení změnit, vyberte **nástroje > Možnosti**, vyberte **zobrazit všechna nastavení** v dolní části dialogového okna, pak přejděte do **textový Editor > Python > Obecné** a vyberte **Čísla řádků**:

    ![Zapnutí číslo řádku pro soubory Python](media/options-general-line-numbers.png)

14. Opravte chybu tak, že změníte `False` argument na řádek 17 `True`. Na řádku, vypadat takto:

    ```python
    self.assertTrue(True) # This should be True
    ```

15. Spusťte program znovu. Pokud Visual Studio zobrazí upozornění o chybách, odpoví **Ano** pokračovat v provozu kód. Pak uvidíte, že předá první kontrola a program se zastaví v další koan. Pokračovat, opravte chyby a program znovu tak, jak chcete.

> [!Important]
> Ve tento rychlý start, kterou jste vytvořili přímé klon *python_koans* úložišti na Githubu. Takové úložiště je chráněný autorem z přímé změny, takže pokus o potvrzení změn do úložiště se nezdaří. V praxi vývojáři místo rozvětvit úložiště k tomuto účtu GitHub, ujistěte se, že změny a vytvořte žádosti o přijetí změn se odeslat tyto změny do původní úložiště. Až budete mít vlastní rozvětvení, použijte místo původní adresu URL úložiště použít dříve jeho adresu URL.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Viz také

- [Ručně identifikace existující překladač Pythonu](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).
- [Instalace podpory Python v sadě Visual Studio 2015 a starší](installing-python-support-in-visual-studio.md).
- [Umístění instalace](installing-python-support-in-visual-studio.md#install-locations).
