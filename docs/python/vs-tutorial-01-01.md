---
title: "Práce s Python v sadě Visual Studio, krok 1 | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
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
ms.openlocfilehash: 07a0b5dbcbb32f7ae8bb7fb4045b55d6aa954f37
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="working-with-python-in-visual-studio"></a>Práce s Python v sadě Visual Studio

Python je oblíbených programovací jazyk, který je spolehlivá, flexibilní, usnadňuje další, bez použití na všech operačních systémech a nepodporuje komunity silné vývojářů a mnoho volné knihovny. Jazyk podporuje všechny způsobů vývoje, včetně webových aplikací, webové služby, aplikace klasické pracovní plochy, skriptování a vědecké výpočty a používá mnoho vysoké školy, vědců, běžné vývojáři a profesionální vývojáře agentem.

Visual Studio poskytuje prvotřídní podporu pro jazyk Python. Tento kurz vás provede následující kroky:

- [Krok 0: instalace](vs-tutorial-01-00.md)
- [Krok 1: Vytvoření projektu jazyka Python (Toto téma)](#step-1-create-a-new-python-project)
- [Krok 2: Zápis a spouštění kódu zobrazíte Visual Studio IntelliSense v práci](vs-tutorial-01-02.md)
- [Krok 3: Vytvoření další kód v okně interaktivní REPL](vs-tutorial-01-03.md)
- [Krok 4: Spuštění programu dokončené v ladicím programu sady Visual Studio](vs-tutorial-01-04.md)
- [Krok 5: Instalace balíčků a správu prostředí Python](vs-tutorial-01-05.md)
- [Krok 6: Práce s Gitem](vs-tutorial-01-06.md)

## <a name="prerequisites"></a>Požadavky

- Visual Studio 2017 se zatížením Python, který je nainstalovaný. V tématu [krok 0](vs-tutorial-01-00.md) pokyny.

## <a name="step-1-create-a-new-python-project"></a>Krok 1: Vytvořte nový projekt Python

A *projektu* je, jak Visual Studio spravuje všechny soubory, které jsou poskytovány společně k vytvoření jedné aplikace, včetně zdrojového kódu, prostředků, konfigurace a tak dále. Projekt aplikaci umožňuje formalizovat a udržuje vztah mezi všechny projektu soubory a také externím prostředkům, které jsou sdíleny více projektů. Jako takový projekt povolí aplikaci snadno rozbalte a růst mnohem jednodušší než jednoduše Správa relací projekt v ad hoc složek, skriptů, textové soubory a i svoje vlastní rozhodnutí.

V tomto kurzu začnete s Jednoduchý projekt obsahující soubor jeden, prázdný kód.

1. V sadě Visual Studio, vyberte **soubor > Nový > projekt** (Ctrl + Shift + N), který spustí **nový projekt** dialogové okno. Zde můžete procházet šablony napříč různými jazyky, pak vyberte jednu pro svůj projekt a určete, kde umístí soubory v sadě Visual Studio.

1. Chcete-li zobrazit šablony Python, vyberte **nainstalovaná > Python** na levé straně, nebo hledáním "Python". Pomocí vyhledávání je skvělým způsobem, jak najít šablonu, pokud si nepamatujete jeho umístění ve stromové struktuře jazyky.

    ![Dialogové okno Nový projekt se zobrazí projektů v jazyce Python](media/vs-getting-started-python-01-new-project.png)

    Všimněte si, jak podporu jazyka Python v sadě Visual Studio obsahuje několik šablon projektu, včetně webových aplikací pomocí rozhraní Bottle, Flask a Django. Pro účely tohoto návodu ale Začněme s prázdným projektem.

1. Vyberte **aplikace Python** šablony, zadejte název projektu a vyberte **OK**. 

1. Po chvíli se Visual Studio zobrazí strukturu projektu v **Průzkumníku řešení** okno (1). Výchozí soubor kód je otevřen v editoru (2). Okno vlastností (3) je také zobrazit další informace o libovolnou položku vybraného v Průzkumníkovi řešení, včetně jeho přesné umístění na disku.

    ![Průzkumník řešení s projektem Python](media/vs-getting-started-python-02-windows.png)

1. Chvíli trvat Seznamte se s Průzkumníku řešení, která je, kde Procházet soubory a složky ve vašem projektu.

    ![Průzkumník řešení rozbalit a zobrazit různé funkce](media/vs-getting-started-python-03-solution-explorer.png)

    (1) zvýrazněná tučným písmem je váš projekt pomocí názvu, který jste zadali v dialogovém okně Nový projekt. Na disku, je reprezentována tento projekt `.pyproj` soubor ve složce projektu.

    (2) na nejvyšší úrovni je *řešení*, který ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentována `.sln` souboru na disku, je kontejner pro jeden nebo více souvisejících projekty. Například pokud napíšete rozšíření C++ pro vaši aplikaci Python, daného projektu C++ může nacházet ve stejném řešení. Řešení může také obsahovat projekt pro webové služby, spolu s projekty pro vyhrazené testovací programy. 

    (3) v rámci projektu najdete zdrojových souborů, v tomto případě jediným `.py` souboru. V okně vlastností výběr soubor zobrazí jeho vlastnosti. Dvojitým kliknutím soubor otevře v jakémkoli způsob je vhodný pro tento soubor.

    (4) v rámci projektu je také **prostředí Python** uzlu. Pokud rozšiřovat, uvidíte dostupné překladače Python, které jsou k dispozici. Rozbalte uzel překladač zobrazíte knihovny, které jsou nainstalovány do prostředí (5).

    Klikněte pravým tlačítkem na libovolný uzel nebo položky v Průzkumníku řešení pro přístup k nabídce použít příkazy. Například **přejmenovat** příkaz umožňuje změnit název libovolný uzel nebo položky, včetně projektu a řešení.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Psaní a spuštění kódu](vs-tutorial-01-02.md)

## <a name="going-deeper"></a>Budete hlubší

- [Python projekty v sadě Visual Studio](python-projects.md).
- [Další informace o jazyka Python na python.org](https://www.python.org)
- [Python pro začátečníky](https://www.python.org/about/gettingstarted/) (python.org)
- [Volné kurzy Pythonu na webu Microsoft Virtual Academy](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Horní Python dotazy na Microsoft Virtual Academy](https://aka.ms/mva-top-python-questions)
