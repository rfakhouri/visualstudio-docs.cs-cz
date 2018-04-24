---
title: Práce s Python, krok 4, ladění
description: Krok 4 základní kurz pro práci s Pythonem v sadě Visual Studio, ke spouštění kódu jazyka Python v ladicím programu.
ms.date: 03/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: c3241adb4afdc18a8ca9a6d4c75f0ee8c80be7b7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="step-4-running-code-in-the-debugger"></a>Krok 4: Spuštění kódu v ladicím programu

**Předchozí krok: [pomocí interaktivních okna REPL](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md)**

Kromě správy projektů, zajištění s formátováním úpravy prostředí a okno interaktivní Visual Studio poskytuje plné ladění pro kód Python. V ladicím programu můžete spustit kód krok za krokem, včetně každé iteraci smyčky. Je také možné pozastavit program vždy, když byly splněné určité podmínky. V libovolném bodě při program kurzoru v ladicím programu, můžete zkontrolovat stav celého programu a změňte hodnotu proměnné. Tyto akce jsou nezbytné pro sledování dolů program chyby a poskytují velmi užitečné pomůcek pro pečlivě následující toku přesný programu.

1. Nahraďte kód v `PythonApplication1.py` souboru následujícím kódem. Případný rozdíl kód rozšiřuje `make_dot_string` tak, aby můžete zkontrolovat jeho diskrétní kroky v ladicím programu. Také zobrazuje `for` cykly do `main` funkce a explicitně spustí při volání této funkce:

    ```python
    from math import cos, radians

    # Create a string with spaces proportional to a cosine of x in degrees
    def make_dot_string(x):
        rad = radians(x)                             # cos works with radians
        numspaces = int(20 * cos(radians(x)) + 20)   # scale to 0-40 spaces
        st = ' ' * numspaces + 'o'                   # place 'o' after the spaces
        return st

    def main():
        for i in range(0, 1800, 12):
            s = make_dot_string(i)
            print(s)

    main()
    ```

1. Zkontrolujte, zda kód funguje správně stisknutím klávesy F5 nebo výběr **ladění > Spustit ladění** příkazu nabídky. Tento příkaz spustí kód v ladicím programu, ale vzhledem k tomu, že jste to neudělali nic pozastavit program, když je spuštěná, právě vytiskne wave vzor několik iterací. Stisknutím libovolné klávesy zavřete okno výstup.

    > [!Tip]
    > Zavřete okno výstup automaticky po dokončení programu, nahraďte `main()` volání následujícím kódem:
    >
    > ```python
    > if __name__ == "__main__":
    >     sys.exit(int(main() or 0))
    > ```

1. Nastavit zarážky `for` příkaz jedním klepnutím na okraji šedé daného řádku nebo umístění pomocí kurzoru do daného řádku a pomocí **ladění > Přepnout zarážku** příkazu (F9). Červené tečky se zobrazí v šedé okraj udávajících zarážek (jak je uvedeno níže šipkou):

    ![Nastavení boru přerušení](media/vs-getting-started-python-18-debugging1.png)

1. Spuštění ladicího znovu (F5) a že spuštěn zastaví kódu na řádku s této zarážek. Zde si můžete prohlédnout volání zásobníku a prozkoumat proměnné. Proměnné, které jsou v oboru zobrazí v **automobily** okno při jejich jste definované; můžete také přepínač tak, aby **místní hodnoty –** zobrazení v dolní části tohoto okna zobrazíte všechny proměnné sadou Visual Studio najde v aktuální obor (včetně funkce), i před jejich jste definovaný:

    ![Breakpoint – uživatelské rozhraní pro jazyk Python](media/vs-getting-started-python-19-debugging2b.png)

1. Sledujte ladění panelu nástrojů (viz následující obrázek) v horní části okna Visual Studio. Tento panel poskytuje rychlý přístup k nejčastěji používané příkazy ladění (který se nachází také na **ladění** nabídky):

    ![Základní ladění tlačítka panelu nástrojů](media/vs-getting-started-python-20-debugging3.png)

    Tlačítka zleva doprava následujícím způsobem:
    - **Pokračovat** (F5) spustí program, dokud na další zarážku nebo až do dokončení programu.
    - **Rozdělit všechny** (Ctrl + Alt + Break) pozastaví dlouho běžící program.
    - **Zastavte ladění** (Shift + F5) program zastaví, pokud je to je a ukončení ladicího programu.
    - **Restartujte** (Ctrl + Shift + F5) program zastaví, pokud je to je a restartuje ho od začátku v ladicím programu.
    - **Zobrazit další příkaz** (Alt + Num *) přepne na další řádek kód pro spuštění. Toto je užitečný zejména při navigaci v kódu během relace ladění a chcete rychle vrátit do bodu, kde je pozastaven ladicího programu.
    - **Krokovat s vnořením** (F11) běží na další řádek kódu, v rámci volaných funkcí.
    - **Krokovat s přeskočením** (F10) běží na další řádek kódu bez nutnosti zadávat do volaných funkcí.
    - **Krokovat s Vystoupením** (Shift + F11) spouští zbytek funkci current a pozastaví v volání kódu.

1. Krok přes `for` příkaz pomocí **Krokovat s přeskočením**. *Krokování s* znamená, že ladicí program spustí aktuálního řádku kódu, včetně volání funkce a pak okamžitě pozastaví znovu. Všimněte si jak proměnnou `i` je nyní definována ve **místní hodnoty –** a **automobily** systému windows.

1. Krok v dalším řádku kódu, který volá `make_dot_string` a pozastaví. Krokovat s přeskočením zde konkrétně znamená, že ladicí program spouští celé `make_dot_string` a když se vrátí. Ladicí program nezastaví uvnitř této funkce, pokud existuje samostatné zarážek existuje.

1. Krokování přes kód několik vícekrát pokračovat a sledovat, jak hodnoty v **místní hodnoty –** nebo **automobily** okno změnit.

1. V **místní hodnoty –** nebo **automobily** poklikejte na soubor v okně **hodnotu** sloupec pro buď `i` nebo `s` proměnné, které chcete upravit hodnotu. Stiskněte klávesu Enter nebo klikněte na tlačítko mimo tuto hodnotu, aby byly použity všechny změny.

1. Pokračovat v procházení kódu pomocí **Krokovat s vnořením**. Krokovat s vnořením znamená, že zadá ladicího programu v žádném volání funkce, pro kterou má ladicí informace, jako například `make_dot_string`. Jednou uvnitř `make_dot_string` můžete zkontrolovat její místní proměnné a konkrétně projděte jeho kód.

1. Krokování s Krokovat s vnořením pokračovat a Všimněte si, že když dosáhnout konce `make_dot_string`, vrátí další krok `for` smyčky s novou hodnotou vrácenou v `s` proměnné. Jako můžete znovu na krok `print` prohlášení, Všimněte si, že Krokovat s vnořením na `print` nevstupuje do této funkce. Důvodem je, že `print` není napsané v Pythonu, ale je místo nativního kódu uvnitř modul Python runtime.

1. Pokračovat v používání Krokovat s vnořením, dokud jste znovu partway do `make_dot_string`. Potom pomocí **Krokovat s Vystoupením** a Všimněte si, že se vrátíte na `for` smyčky. Ladicí program s Krokovat s Vystoupením, spustí zbytek funkce a automaticky pozastaví v volání kódu. To je velmi užitečné, když jste provedl některé část zdlouhavé funkce, kterou chcete ladit, ale nepotřebujete krok procházení zbytku a nebudete chtít nastavit explicitní zarážek v volání kódu.

1. Chcete-li pokračovat, spuštění programu, dokud nebude dosaženo další zarážku, použijte **pokračovat** (F5). Vzhledem k tomu, že máte zarážky ve `for` smyčky, rozdělit na další iterace.

1. Procházení stovky iterace smyčky může to být zdlouhavé, takže Visual Studio můžete přidat *podmínku* k zarážky. Ladicí program pak pozastaví programu u zarážky jenom v případě, že je splněna podmínka. Například můžete použít podmínku se zarážkou na `for` prohlášení, které se pozastaví pouze při hodnotě `i` překračuje 1 600. Pokud chcete nastavit tuto podmínku, klikněte pravým tlačítkem na red zarážek tečky a vyberte **podmínky...** (Alt + F9, C). V **nastavení zarážek** překryvné okno zobrazené, zadejte `i > 1600` jako výraz a vyberte **Zavřít**. Stisknutím klávesy F5 pokračovat a pozorovat, že se program spouští mnoho iterací před koncem Další.

    ![Nastavení zarážek podmínku](media/vs-getting-started-python-21-debugging4.png)

1. Chcete-li spustit program dokončen, zakázat zarážce kliknete pravým tlačítkem a výběrem **zakázat zarážek** (Ctrl + F9). Potom vyberte **pokračovat** (nebo stiskněte klávesu F5) ke spuštění programu. Při ukončení programu sady Visual Studio zastaví jeho relaci ladění a vrátí jeho režimu úprav. Všimněte si, že můžete také odstranit zarážce kliknutím jeho tečku, ale to také odstraní všechny podmínky, které jste nastavili.

> [!Tip]
> V některých situacích, jako je například selhání při spuštění překladač Pythonu, samostatně může ve výstupním okně zobrazí pouze stručně a pak zavřete automaticky bez s možností zobrazíte všechny chyby zprávy. Pokud k tomu dojde, klikněte pravým tlačítkem na projekt v Průzkumníku řešení, vyberte **vlastnosti**, vyberte **ladění** kartě a pak přidejte `-i` k **překladač argumenty** pole. Tento argument způsobí, že překladač uvést do režimu interaktivní po dokončení programu, a tím zprovozní okno Otevřít zadejte Ctrl + Z, zadejte ukončíte.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Instalace balíčků ve vašem prostředí Python](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)

### <a name="going-deeper"></a>Budete hlubší

- [Ladění](debugging-python-in-visual-studio.md)
- [Ladění v sadě Visual Studio](../debugger/debugger-feature-tour.md) poskytuje úplnou dokumentaci sady Visual Studio je ladění funkcí.
