---
title: Práce s kurzu Python, krok 3 interaktivních okna REPL
description: Krok 3 průvodce základní možnosti Python v sadě Visual Studio, pokrývajících okno REPL interaktivní Python.
ms.date: 01/16/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 3d5d0224c9f6d8d76f73c79feeaa363a6e0a954a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-3-using-the-interactive-repl-window"></a>Krok 3: Použití okna interaktivní REPL

**Předchozí krok: [zápisy a spuštěného kódu](tutorial-working-with-python-in-visual-studio-step-02-writing-code.md)**

Visual Studio *interaktivních okna* pro jazyk Python poskytuje prostředí bohaté čtení vyhodnotit tisk smyčky (REPL), který výrazně zkracuje obvyklé cyklus úpravy – sestavení – ladění. Okno interaktivní nabízí všechny funkce prostředí REPL Python příkazového řádku. Také usnadňuje velmi k výměně kód s zdrojové soubory v sadě Visual Studio editor, který je jinak komplikované pomocí příkazového řádku.

1. Otevřete okno interaktivní kliknutím pravým tlačítkem na prostředí Python projektu v Průzkumníku řešení (například "Python 3.6 (32 bitů)" ukazuje předchozí obrázek) a výběrem **otevřete okno interaktivní**. Případně můžete vybrat **zobrazení > ostatní okna > Windows interaktivní Python** z hlavní nabídky v sadě Visual Studio.

1. Otevře se okno interaktivní níže editoru se standardem `>>>` Python REPL řádku. **Prostředí** rozevíracího seznamu můžete vybrat konkrétní překladač pro práci s. Často je také vhodné interaktivní okno větší, což lze provést tak, že přetáhnete oddělovač mezi dvěma windows:

    ![Interaktivní okno Python a přetáhnete ke změně velikosti](media/vs-getting-started-python-11-interactive1b.png)

    > [!Tip]
    > Můžete nastavit velikost všech oken v sadě Visual Studio tak, že přetáhnete příhraničních oddělovačů. Můžete také přetáhněte windows nezávisle na rámečku Visual Studio a změna uspořádání, je ale chcete do rámečku. Úplné podrobnosti najdete v tématu [přizpůsobení rozložení oken](../ide/customizing-window-layouts-in-visual-studio.md).

1. Zadejte pár příkazy, jako je třeba `print("Hello, Visual Studio")` a výrazy, jako jsou `123/456` a zobrazte okamžitou výsledky:

    ![Výsledky okamžitou interaktivní okno Python](media/vs-getting-started-python-12-interactive2.png)

1. Když spustíte Víceřádkový příkazů, jako je definici funkce interaktivních okna zobrazuje jazyka Python `...` výzva k pokračování řádky, které na rozdíl od příkazového řádku REPL poskytuje automatické odsazení:

    ![Interaktivní okno Python s pokračování – příkaz](media/vs-getting-started-python-13-interactive3.png)

1. Interaktivní okno poskytuje úplnou historii všechno, co jste zadali a vylepšuje příkazového řádku REPL pomocí víceřádkovým historie položky. Například můžete snadno odvolat celý definice `f` fungovat jako na jednu jednotku a snadno změnit název, který má `make_double`, místo opětovné vytvoření funkce řádek po řádku.

1. Visual Studio můžete odeslat více řádků kódu z editoru okna interaktivních okna. Tato funkce umožňuje udržovat kód v souboru zdroje a snadno odeslat vyberte části okna interaktivní. Potom můžete pracovat s tyto fragmenty kódu v rychlé prostředí REPL namísto nutnosti spuštění celého programu. Pokud chcete zobrazit tuto funkci, nejprve nahradit `for` smyčky v `PythonApplication1.py` soubor s následující:

    ```python
    # Create a string with spaces proportional to a cosine of x in degrees
    def make_dot_string(x):
        return ' ' * int(20 * cos(radians(x)) + 20) + 'o'
    ```

1. Vyberte pouze `import` a `from` příkazy v `.py` soubor, klikněte pravým tlačítkem a vyberte **poslat interaktivní** (nebo stiskněte klávesu Ctrl + Enter). Fragment kódu je okamžitě vložit do okna interaktivní a spustit. Nyní vybrat `make_dot_string` funkce a zopakujte stejný příkaz, který znovu spustí fragmentu kódu. Protože kód definuje funkci, můžete rychle otestovat této funkce voláním několikrát:

    ![Odesílání kódu do interaktivních okna a jeho otestováním](media/vs-getting-started-python-14-interactive4.png)

    > [!Tip]
    > Pomocí kombinace kláves Ctrl + Enter v editoru *bez* výběr běží aktuálního řádku kódu v okně interaktivní a automaticky umístí pomocí kurzoru na další řádek. Pomocí této funkce kombinace kláves Ctrl + Enter opakovaně nabízí pohodlný způsob, jak procházet kód, který není možné pomocí pouze Python příkazového řádku. To také umožňuje krokovat kód bez spuštění ladicího programu a bez vašeho programu nutně od začátku.

1. Můžete také zkopírovat a vložit více řádků kódu do okna interaktivní z jakéhokoli zdroje, jako je například fragmentu níže, které je obtížné provést pomocí příkazového řádku REPL. Python Při vložení, interaktivních okna spustí, tento kód jako kdybyste zadali do:

    ```python
    for i in range(360):
        s = make_dot_string(i)
        print(s)
    ```

    ![Vkládání více řádků kódu pomocí odesílání interaktivní](media/vs-getting-started-python-15-interactive5.png)

1. Jak můžete vidět, tento kód funguje bez problémů, ale není velmi inspiring její výstup. Hodnota různých kroku v `for` smyčky by zobrazuje víc kosinus wave. Naštěstí protože celý `for` smyčky v historii REPL jako na jednu jednotku, je snadné a vraťte se a provádět jakékoliv změny můžete chcete a k testování funkce znovu. Stisknutím klávesy šipka nahoru první odvolání `for` smyčky. Stiskněte klávesu šipky doleva nebo doprava zahájíte navigace v kódu (dokud tak nahoru a dolů šipky nadále procházení historie). Přejděte do a změnit `range` specifikace `range(0, 360, 12)`. Ke spuštění celý příkaz znovu stiskněte kombinaci kláves Ctrl + Enter (kdekoli v kódu):

    ![Úpravy předchozí příkaz v okně interaktivní](media/vs-getting-started-python-16-interactive6.png)

1. Opakujte tento postup a experimentovat s nastavení různých krok, dokud najít hodnotu, které vám nejvíce líbí. Můžete provést také wave opakování prodlužte rozsahu, například `range(0, 1800, 12)`.
 
1. Až budete spokojeni s kódem se zapisují v okně interaktivní, vyberte ho, klikněte pravým tlačítkem a vyberte **kopie kódu** (Ctrl + Shift + C) a potom vložit do editoru. Všimněte si, jak tato speciální funkce sady Visual Studio automaticky vynechá žádný výstup a taky `>>>` a `...` zobrazí výzvu. Například následující obrázek ukazuje, pomocí **kopie kódu** na výběr, který zahrnuje výzvy a výstup příkazu:

    ![Příkaz kódu kopie interaktivních okna na výběru s výzvami a výstup](media/vs-getting-started-python-17-interactive7.png)

    Když vložíte do editoru, zobrazí se pouze kód:

    ```python
    for i in range(0, 1800, 12):
        s = make_dot_string(i)
        print(s)
    ```

    Pokud chcete zkopírovat přesný obsah interaktivních okna, včetně pokynů a výstup, použijte standardní **kopie** příkaz.

1. Co jste právě provedli je vycházejí z podrobností o malou část kódu pomocí rychlé prostředí REPL interaktivních okna a potom pohodlně přidat tento kód do vašeho projektu zdrojový soubor. Když nyní spustíte kód znovu pomocí kombinace kláves Ctrl + F5 (nebo **ladění > Spustit bez ladění**), najdete v části chtěli byste přesné výsledky.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Spuštěním kódu v ladicím programu](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)

## <a name="going-deeper"></a>Budete hlubší

- [Pomocí interaktivních okna](python-interactive-repl-in-visual-studio.md)
- [Použití IPythonu REPL](interactive-repl-ipython.md)
