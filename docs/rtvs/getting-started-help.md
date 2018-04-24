---
title: Okno nápovědy pro R
description: Nápověda pro R je implementovaná přímo do okna interaktivní v sadě Visual Studio prostřednictvím? Příkaz.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 6153a59e1875bf7b1dd81e794e0d15a37d47c2f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="help-in-r-tools-for-visual-studio"></a>Nápověda v R nástrojů pro Visual Studio

Nápověda pro R je implementovaná přímo do okna interaktivní v sadě Visual Studio. Vždy, když použijete `?` příkazu, například `?mtcars`, Nápověda v dokumentaci k R se zobrazí v okně Visual Studio:

![Okno nápovědy v sadě Visual Studio](media/help-window.png)

> [!Tip]
> V okně nápovědy, stejně jako všechny ostatní v sadě Visual Studio, můžete uspořádané a ukotven, ale chcete. V tématu [přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md).
>
> V prohlížeči otevřete nápovědy výsledky, vyberte **R nástroje > Možnosti** nabídky a sady **R pomoci prohlížeče** vlastnost `External`. V tématu [možnosti](options-for-r-tools-in-visual-studio.md).

Chcete-li v nápovědě, použijte `??` příkazu s parametrem hledaný termín. Pokud hledaný termín obsahuje mezery, použijte uvozovky:

```R
??"Motor Trend"
```

![Výsledky hledání nápovědy](media/help-search1.png)

V okně nápovědy má také vyhledávání vstupní pole, pomocí kterého můžete provést další hledání v dokumentaci k R přímo:

![Výsledky hledání nápovědy podle pole](media/help-search2.png)

## <a name="integrated-help-lookup"></a>Vyhledávání integrované nápovědy

Vývojáři často vyhledejte v dokumentaci R nápovědu k názvy funkcí, datové sady a další elementy. R nástrojů pro Visual Studio (RTVS) zjednodušuje proces integrací hledání nápovědy přímo do editoru a interaktivní windows.

- Stisknutím klávesy F1 během automatického dokončování operace vytvoří seznam výsledků nápovědy, které odpovídají dílčí řetězec.
- Pravým tlačítkem myši na hledaný termín (např. funkce) a výběrem **nápovědy na** příkaz otevře nápovědu pro tuto funkci. Můžete také vyvolat **nápovědy na** pro všechny výběr.

    ![Volajícím pomoc prostřednictvím v místní nabídce klikněte pravým tlačítkem](media/help-right-click.png)

> [!Tip]
> V prohlížeči otevřete integrované nápovědy, vyberte **R nástroje > Možnosti** a nastavte **F1 webový prohlížeč** k `External`. V tématu [možnosti](options-for-r-tools-in-visual-studio.md).

## <a name="integrated-stackoverflow-search"></a>Integrované hledání StackOverflow

Kromě hledání v dokumentaci k R, vývojáři často vyhledávání StackOverflow při psaní kódu. RTVS zjednodušuje také tohoto procesu. Klikněte pravým tlačítkem na termín nebo výběr, vyberte **Hledat na webu pro** příkazu (Ctrl + F1) a Visual Studio otevře okno s výsledky hledání rozsah StackOverflow:

![Výsledky hledání web v sadě Visual Studio](media/help-web-search-results.png)

Připojením oboru řetězec, můžete změnit `R site:stackoverflow`, až **R nástroje > Možnosti > F1 webové hledaný řetězec** možnost:

![Změna možnost F1 webové hledání řetězce](media/options-dialog.png)

Pokud chcete zobrazit výsledky v prohlížeči, změnit **F1 webový prohlížeč** možnost, jak je popsáno na [možnosti](options-for-r-tools-in-visual-studio.md).