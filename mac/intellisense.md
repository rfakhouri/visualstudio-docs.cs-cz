---
title: IntelliSense
description: Informace o použití IntelliSense v Visual Studio pro Mac
author: cobey
ms.author: cobey
ms.date: 08/16/2019
ms.openlocfilehash: 3e99c31b1ab4d12532d701e4626ac9c1aae7df56
ms.sourcegitcommit: 0bd63f3bc429ae059b9df6e45c6b8dcae6152940
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/26/2019
ms.locfileid: "70026957"
---
# <a name="intellisense"></a>IntelliSense

Technologie IntelliSense poskytuje několik funkcí, které vám pomůžou zlepšit možnosti psaní a úprav kódu. Například kromě dokončování kódu poskytuje modul IntelliSense také seznamy členů, informace o parametrech a rychlé informace.

V Visual Studio pro Mac je technologie IntelliSense poskytována pomocí základní služby editoru a je podporována v mnoha jazycích, například C#XAML, F#, JavaScript a dalších. Visual Studio pro Mac také obsahuje pokročilé funkce technologie IntelliSense, jako je například schopnost zobrazit dokončování z knihoven, které ještě nejsou naimportovány do projektu.

## <a name="code-completion"></a>Dokončování kódu

Při psaní v rámci podporovaného souboru, jako je C# například soubor kódu, se v seznamu pro doplňování zobrazí platné dokončování pro řetězec, který právě píšete a který se aktualizuje při psaní. Kromě toho, pokud odstraníte text, seznam se znovu automaticky aktualizuje, aby zahrnoval širší rozsah možností pro dokončení daného řetězce. 

Okno dokončení také nabízí podporu pro filtrování zahrnutých dokončení podle typu. Například je možné omezit členy seznamu tak, aby představovaly pouze typy, jako jsou třídy nebo Delegáti. Tento proces filtrování lze povolit buď kliknutím na konkrétní ikonu představující typ, který bude filtrován nebo prostřednictvím klávesových zkratek, které odpovídají danému typu. Ikony, které jsou umístěny v dolní části okna dokončení, jsou následující:

| Ikona                         | Name          | Klíčové slovo    | Klávesová zkratka |
| -----------------------------|---------------| -----------|--------|
| ![Ikona třídy](media/classes-icon.png)  | třída         | `class`    |  ⌥ C
| ![Ikona konstanty](media/constant-icon.png) | – konstanta      | `const`    |  ⌥ O
| ![Ikona delegáta](media/delegate-icon.png) | delegát      | `delegate` |  ⌥ D
| ![Ikona výčtu](media/enums-icon.png)    | enum          | `enum`     |  ⌥ E
| ![Ikona události](media/event-icon.png)    | event         |            |  ⌥ V
| ![Ikona pole](media/fields-icon.png)   | pole         |            |  ⌥ F
| ![Ikona rozhraní](media/interface-icon.png)| rozhraní     | `interface`|  ⌥ I
| ![Ikona klíčového slova](media/keyword-icon.png)  | klíčové slovo       |            |  ⌥ K
| ![Ikona metody](media/method-icon.png)   | – metoda        |            |  ⌥ M
| ![Ikona oboru názvů](media/namespace-icon.png)| – obor názvů     | `namespace`|  ⌥ N
| ![Ikona props](media/props-icon.png)    | property      |            |  ⌥ P
| ![Ikona fragmentu](media/snippet-icon.png)  | zlomk       | `class`    |  ⌥ S
| ![Ikona struktury](media/struct-icon.png)   | – struktura     | `struct`   |  ⌥ S

Kliknutím na některou z ikon nebo stisknutím odpovídajících klávesových zkratek se seznam dokončení omezí jenom na typy, které definuje sada filtrů.  

![Filtrování typu IntelliSense](media/intellisense-typefiltering.gif)

## <a name="show-import-items"></a>Zobrazit položky importu

Ve výchozím nastavení bude dokončování technologie IntelliSense zobrazovat pouze dokončování z knihoven, které byly importovány do projektu. Pokud `System.Collections.Generic` jste například neimportovali přes `using` , nebudete mít k `List<>`dispozici žádné dokončení. Chcete-li zobrazit dokončování z knihoven, které nejsou naimportovány, je nutné povolit možnost **Zobrazit import položek** v rámci předvoleb pro Visual Studio pro Mac. Toto nastavení najdete v části **předvolby > textový Editor > IntelliSense**:

![IntelliSense – zobrazit položky importu](media/intellisense-showimport.png)

Jakmile je možnost **Zobrazit položky importu** povolena, bude seznam dokončení zahrnovat dokončování, které jste ještě neimportovali. Po výběru položky, která odpovídá nedeklarované knihovně, `using` bude příkaz pro tuto knihovnu automaticky přidán do hlavičky souboru kódu. Název knihovny, do které dokončí doplňování, je také uveden spolu se samotným dokončením.

![Zobrazit seznam položek importu](media/intellisense-importaction.png)

## <a name="parameter-window"></a>Okno parametrů

Další funkcí technologie IntelliSense je možnost poskytnout seznam parametrů tam, kde je to vhodné. Seznam parametrů poskytuje podrobné informace o signaturách metody pro volání kódu. Kliknutím na šipky nahoru/dolů v rámci podpisu můžete cyklicky procházet jednotlivé dostupné signatury parametrů, abyste určili nejvhodnější požadavky. Kromě podrobností o povolených typech dat může být také popis definovaný v cílové metodě prostřednictvím komentářů XML.

![Seznam parametrů](media/intellisense-parameter.png)

Při vyplňování parametrů bude mít parametr, který právě upravujete, tučný, zatímco neaktivní parametry budou mít standardní váhu. 


## <a name="triggering-completion-window-and-parameter-window"></a>Aktivace okna dokončení a okna parametrů

Okno dokončování se automaticky aktivuje při psaní v rámci zdrojového souboru. Můžete ale také aktivovat okno dokončení pomocí zástupce `control-space`. Tato kombinace kláves způsobí, že se seznam dokončení zobrazí na aktuální pozici blikajícího kurzoru. 

Můžete také ručně aktivovat vzhled okna parametrů zadáním `control-shift-space`. Když je blikající kurzor na pozici, která je platná pro seznam parametrů, seznam parametrů se zobrazí poblíž pozice blikajícího kurzoru.

## <a name="see-also"></a>Viz také:

- [Rychlé akce (Visual Studio ve Windows)](/visualstudio/ide/quick-actions)
- [Refaktoring kódu (Visual Studio ve Windows)](/visualstudio/ide/refactoring-in-visual-studio)
