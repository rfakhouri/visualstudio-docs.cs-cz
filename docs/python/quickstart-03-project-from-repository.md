---
title: "Rychlý úvod: Klonování úložiště Python kódu v sadě Visual Studio | Microsoft Docs"
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
ms.openlocfilehash: 5ce79d4e8ff2056b5d713eaa781b22359141c9b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-clone-a-repository-of-python-code-in-visual-studio"></a>Rychlý úvod: klonovat úložiště Python kódu v sadě Visual Studio

Jakmile jste [nainstalována podpora v jazyce Python ve Visual Studio 2017](installation.md), můžete snadno klonovat úložiště v kódu jazyka Python a vytvořte projekt z něj.

[!INCLUDE[install-github-extension](includes/install-github-extension.md)]

2. Spusťte sadu Visual Studio.

3. Vyberte **zobrazení > Team Explorer...**  otevřete **Team Explorer** okno, ve kterém můžete připojit k webu GitHub nebo Visual Studio Team Services, nebo klonovat úložiště.

    ![Team explorer okno zobrazující Visual Studio Team Services, GitHub a klonování úložiště](media/team-explorer.png)

4. Do pole Adresa URL v části **místní úložiště Git**, zadejte `https://github.com/gregmalcolm/python_koans`, zadejte složku pro klonovaný soubory a vyberte **klon**.

    > [!Tip]
    > Složky, kterou zadáte v Team Explorer je konkrétní složky přijímat klonovaný soubory. Na rozdíl od `git clone` příkazu vytvoříte klon v Team Exploreru nevytvoří automaticky podsložku s názvem úložiště.

5. Po dokončení klonování dvakrát klikněte na složku úložiště v dolní části Team Explorer a přejděte na řídicí panel úložiště. V části **řešení**, vyberte **nový...** .

    ![Okno Průzkumníka týmu, vytvoření nového projektu z klonu](media/team-explorer-new-project.png)

6. V **nový projekt** dialog, který se zobrazí, vyberte "Z existující kód Python", zadejte název projektu, nastavte **umístění** do stejné složky jako úložiště a vyberte **OK**. V průvodci, který se zobrazí, vyberte **Dokončit**.

7. Vyberte **zobrazení > Průzkumníku řešení** z nabídky.

8. V Průzkumníku řešení rozbalte `python3` uzel, klikněte pravým tlačítkem na `contemplate_koans.py`a vyberte **nastavit jako spouštěcí soubor**. Tento krok informuje soubor, který se má používat při spuštění projektu sady Visual Studio.

9. Vyberte **Projekt > vlastnosti** v nabídce vyberte **Obecné** kartě a nastavte **pracovní adresář** na "python3". To je nezbytné, protože ve výchozím nastavení sady Visual Studio nastavuje pracovní adresář na kořenu projektu a nikoli umístění souboru spuštění (`python3\contemplate_koans.py`, který se zobrazí ve vlastnostech projektu). Kód programu hledá soubor `koans.txt` v pracovní složku, tak bez změnou této hodnoty se zobrazí chyba za běhu.

    ![Nastavení pracovní adresář pro projekt Python](media/projects-set-working-directory.png)

10. Stiskněte klávesy Ctrl + F5 nebo vyberte **ladění > Spustit bez ladění** ke spuštění programu. Pokud se zobrazí `FileNotFoundError` pro `koans.txt`, znovu zkontrolujte pracovní adresář nastavení v předchozím kroku.

11. Když se program spouští úspěšně, zobrazí chybu kontrolní výraz na řádku 17 `python3/koans/about_asserts.py`. To je úmyslné: program navrženy tak, aby Python tak, že jste opravte všechny chyby záměrné. (Další informace najdete na [Ruby Koans](http://rubykoans.com/), které daly podnět Python Koans.)

    ![První výstup z programu koans Python](media/koans-output.png)

12. Otevřete `python3/koans/about_asserts.py` tak, že přejdete k němu v Průzkumníku řešení a dvojitým kliknutím na soubor. Všimněte si, že čísla řádků se nezobrazí ve výchozím nastavení v editoru. Chcete-li toto nastavení změnit, vyberte **nástroje > Možnosti**, vyberte **zobrazit všechna nastavení** v dolní části dialogového okna, pak přejděte do **textový Editor > Python > Obecné** a vyberte **Čísla řádků**:

    ![Zapnutí číslo řádku pro soubory Python](media/options-general-line-numbers.png)

13. Opravte chybu tak, že změníte `False` argument na řádek 17 `True`. Na řádku, vypadat takto:

    ```python
    self.assertTrue(True) # This should be True
    ```

14. Spusťte program zjistíte, že první kontrola předá a program se zastaví v další koan. Pokračujte, opravte chyby a opětovné spuštění programu, jak chcete.

> [!Important]
> Ve tento rychlý start, kterou jste vytvořili přímé klon *python_koans* úložišti na Githubu. Takové úložiště je chráněný autorem z přímé změny, takže pokus o potvrzení změn do úložiště se nezdaří. V praxi vývojáři místo rozvětvit úložiště k tomuto účtu GitHub, ujistěte se, že změny a vytvořte žádosti o přijetí změn se odeslat tyto změny do původní úložiště. Tyto kroky jsou popsané v [kurzu kroku 6 – práce s Gitem](vs-tutorial-01-06.md).

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](vs-tutorial-01-01.md)

## <a name="see-also"></a>Viz také

- [Vytvoření prostředí pro existující překladač Pythonu](python-environments.md#creating-an-environment-for-an-existing-interpreter).
- [Instalace podpory Python v sadě Visual Studio 2015 a starší](installation.md).
- [Umístění instalace](installation.md#install-locations).
