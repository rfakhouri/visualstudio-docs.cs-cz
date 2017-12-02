---
title: "Práce s Python v sadě Visual Studio, krok 2 | Microsoft Docs"
ms.custom: 
ms.date: 10/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: d417ac531331b62b0f711fe155a94f1ac0954310
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-writing-and-running-code"></a>Krok 2: Psaní a spuštění kódu

**Předchozí krok: [vytvoření nového projektu Python](vs-tutorial-01-01.md)**

Sice Průzkumníku řešení, kde budete spravovat soubory projektu, *editor* okno je obvykle kde pracovat *obsah* souborů, jako zdrojový kód. Editor má zasílat informace o typu souboru, který upravujete, včetně programovací jazyk (založené na příponě souboru) a nabízí funkce vhodné pro daný jazyk, například barevné zvýrazňování syntaxe a automatické dokončování pomocí IntelliSense.

1. Po vytvoření nového projektu "Python aplikace", výchozí prázdný soubor s názvem `PythonApplication1.py` je otevřen v editoru Visual Studio. 

1. V editoru, začněte psát `print("Hello, Visual Studio")` a Všimněte si, jak Visual Studio IntelliSense zobrazí možnosti automatického dokončování na cestě. V rozevíracím seznamu možnost pro popsané je výchozí dokončení, která se používá při stiskněte klávesu Tabulátor. Dokončování jsou nejužitečnější, pokud se podílejí delší příkazy nebo identifikátory.

    ![Místní nabídka Automatické dokončování IntelliSense](media/vs-getting-started-python-04-IntelliSense1b.png)

1. IntelliSense ukazuje různé informace v závislosti na příkaz, kterou používáte, funkce, ke kterému se připojujete a tak dále. S `print` fungovat, zadáním `(` po `print` udávajících funkce volání zobrazí informace o této funkci úplné využití. IntelliSense otevíraném také ukazuje aktuální argument tučným (**hodnotu** jak je vidět tady):

    ![Místní nabídka Automatické dokončování IntelliSense pro funkci](media/vs-getting-started-python-05-IntelliSense2b.png)

1. Proveďte příkaz tak, aby odpovídala následující:

    ```python
    print("Hello, Visual Studio")
    ```

1. Všimněte si, zabarvení syntaxe, která odlišuje příkaz `print` v argumentu `"Hello Visual Studio"`. Navíc dočasně odstranit poslední `"` na řetězce a Všimněte si, jak Visual Studio se zobrazí červený podtržení pro kód který obsahuje syntaktické chyby. Potom můžete nahradit `"` opravit kód.
 
    ![Barevné zvýrazňování syntaxe IntelliSense a zvýraznění chyby](media/vs-getting-started-python-06-IntelliSense3b.png)
 
    > [!Tip]
    > Protože jeden pro vývojové prostředí je velmi osobní záležitosti, Visual Studio poskytuje úplnou kontrolu nad vzhled a chování sady Visual Studio. Vyberte **nástroje > Možnosti** nabídky příkazů a zkontrolovat nastavení v části **prostředí** a **textového editoru** karty. Ve výchozím nastavení se zobrazí pouze omezený počet možností; Pokud chcete zobrazit všechny dostupné možnosti pro každou programovací jazyk, vyberte **zobrazit všechna nastavení** v dolní části dialogových oken. 

1. Spustit kód, který jste zapisovat do tohoto bodu stisknutím Ctrl + F5 nebo výběrem **ladění > Spustit bez ladění** položku nabídky. Visual Studio zobrazí upozornění, pokud máte pořád chyby v kódu.
 
1. Při spuštění programu, zobrazí okno konzoly zobrazení výsledků, stejně, jako kdyby byste spustili překladač Pythonu s `PythonApplication1.py` z příkazového řádku. Stisknutím klávesy zavřete okno a vrátíte se do editoru Visual Studio.

    ![Výstup prvního spuštění programu](media/vs-getting-started-python-07-output.png)

1. Kromě dokončených pro příkazy a funkce, technologie IntelliSense poskytne dokončených pro jazyk Python `import` a `from` příkazy. Tyto dokončených můžete snadno zjistit, jaké moduly jsou dostupné ve vašem prostředí a členy těchto modulů. V editoru, odstraňte `print` řádku a začněte psát `import `. Seznam modulů se zobrazí, když zadáte místo:

    ![Zobrazuje dostupné moduly pro příkaz import IntellSense](media/vs-getting-started-python-08-import1.png)

1. Dokončení řádku zadáním nebo výběrem `sys`.

1. Na následujícím řádku, zadejte `from` znovu zobrazte seznam modulů:

    ![Zobrazuje dostupné moduly pro IntellSense z příkazu](media/vs-getting-started-python-09-import2.png)

1. Vyberte nebo zadejte `math`, pokračujte zadáním mezerou a `import`, který zobrazí členy modul:

    ![IntellSense zobrazující modulu členy](media/vs-getting-started-python-10-import3.png)

1. Dokončit importováním `sin`, `cos`, a `radians` členy, pro každou vašeho povšimnutí dostupné dokončených automaticky. Když jste hotovi, váš kód by měl vypadat takto:

    ```python
    import sys  
    from math import sin, cos, radians          
    ```

    > [!Tip]
    > Dokončování dílčích řetězců pracovat, jako typ, odpovídající části slov, písmena na začátku slova a dokonce přeskočen znaků. V tématu [úpravy kódu - dokončených](code-editing.md#completions) podrobnosti.

1. Přidejte trochu další kód tisknout kosinus hodnoty 360 stupňů:

    ```python 
    for i in range(360):        
        print(cos(radians(i)))
    ```

1. Spusťte program znovu s Ctrl + F5 nebo **ladění > Spustit bez ladění**. Po dokončení zavřete okno výstup.


## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Používání okna interaktivní REPL](vs-tutorial-01-03.md)


## <a name="going-deeper"></a>Budete hlubší

- [Úpravy kódu](code-editing.md)
- [Formátování kódu](code-formatting.md)
- [Refaktoring kódu](code-refactoring.md)
- [Použití PyLintu](code-pylint.md)
