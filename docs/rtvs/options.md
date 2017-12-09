---
title: "R nástroje Možnosti v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords:
- vs.toolsoptionspages.text_editor.r.advanced
- vs.toolsoptionspages.r_tools
- vs.toolsoptionspages.r_tools.advanced
- vs.toolsoptionspages.r_tools.#150
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: dd21ba3c54ed274f181c036ed0121d8d3c5a180e
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="r-tools-for-visual-studio-options"></a>R nástroje pro možnosti aplikace Visual Studio

Možnosti a nastavení, které jsou specifické pro R se přistupuje pomocí níže uvedených způsobů. Je nutné vybrat **zobrazit všechna nastavení** pole v dolní části **možnosti** dialogové okno pro všechny tyto oddíly se objeví.

- Možnosti formátování kódu (v tématu [možností editoru](code-editing.md#editor-options): **nástroje > Možnosti** nabídce pak vyberte **textový Editor > R > formátování**
- Možnosti linting (najdete v části [Linting](code-linting.md)): **nástroje > Možnosti** nabídce pak vyberte **textový Editor > R > hadříkem**
- Rozšířené možnosti editoru ([popsaných v tomto tématu](#text-editor-r-advanced-options)): **nástroje > Možnosti** nabídce pak vyberte **textový Editor > R > Upřesnit**
- Chování možnosti ([popsaných v tomto tématu](#r-tools-advanced-options)): **R nástroje > Možnosti** nabídky, nebo **nástroje > Možnosti**, posuňte se k **R nástroje**.

**R nástroje > Nastavení vědecké účely dat** příkaz ovlivní také řadu různých nastavení v sadě Visual Studio celkové. Tento příkaz je popsaná v další části.

<a name="data-scientist-layout"></a>

## <a name="r-tools--data-science-settings"></a>R nástroje > Nastavení dat vědecké účely

**R nástroje > Nastavení vědecké účely dat** položky nabídky nakonfiguruje rozložení, která je optimalizovaná pro potřeby datových vědců Visual Studio IDE. Konkrétně, otevře tato možnost [interaktivní](interactive-repl.md), [proměnné Explorer](variable-explorer.md), a [pracovních prostorů](workspaces.md) windows:

![Rozložení okna vědecký pracovník data v sadě Visual Studio](media/installation-data-scientist-layout-result.png)

Se později vrátit k jiné nastavení sady Visual Studio, nejprve použijte **nástroje > Nastavení importu a exportu** příkazu, vyberte **Export vybrané nastavení prostředí**a zadejte název souboru. K obnovení těchto nastavení, použijte stejný příkaz a vyberte **importovat vybrané nastavení prostředí**. Můžete také použít stejné příkazy, pokud změníte vědecký pracovník rozložení dat a chcete vrátit k němu později na místo pomocí **nastavení vědecké účely dat** příkaz přímo.

## <a name="text-editor--r--advanced-options"></a>Textový Editor > R > Rozšířené možnosti

Tyto možnosti určují chování formátování, IntelliSense, osnovy, odsazení a syntaxe kontrola R.

![Dialogové okno Možnosti R textového editoru rozšířené možnosti](media/options-dialog-advanced-text-editor.png)

Každý je možnost nastavena na zapnuto nebo vypnuto můžete řídit chování nejistá. Podrobnosti o jednotlivých možností na podívejte se na podokně nápovědy v dolní části dialogových oken. Všimněte si, že přetažením horní části podokna této nápovědy až zkontrolujte podokně větší.

![Rozšířit podokno Nápověda v dialogovém okně R editor text rozšířené možnosti](media/options-dialog-advanced-text-editor2.png)

## <a name="r-tools--advanced-options"></a>R nástroje > Rozšířené možnosti

**R nástroje > Možnosti** otevře příkazu v nabídce **možnosti** dialogové okno Možnosti R:

  ![Dialogové okno Možnosti nástroje R](media/options-dialog.png)

Následující části popisují různé možnosti, které jsou k dispozici na této stránce.

### <a name="debugging"></a>Ladění

Tyto možnosti určují způsob zpracování hodnot v [proměnné Explorer](variable-explorer.md) a ladicí program windows jako sledování a lokální proměnné (najdete v části [ladění](debugging.md)).

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Vyhodnocení active vazby | `True` | Když `True`, zajišťuje při kontrole proměnné a vlastnosti vždy najdete aktuální hodnotu. Riziko je, že vyhodnocení výrazů může způsobit vedlejší účinky, v závislosti na tom, jak byly implementovány. |
| Zobrazit předponu tečkou proměnné | `False` | Určuje, zda proměnné předponu `.` jsou zobrazeny. |

### <a name="grid-view"></a>Zobrazení mřížky

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Dynamické vyhodnocení | `False` | Ve výchozím nastavení `View(<expression>)` funkce pořídí snímek dat jako snímek dat, který může spotřebovat značnou část paměti s velkých datových sad. Nastavení této možnosti na `True` znamená, že je tento výraz vyhodnocen při mřížky aktualizuje načíst pouze data, která se zobrazí. Ale pokud změny výraz data také změní, což může být není vhodný pro dplyr pip výrazy. |

### <a name="help"></a>Nápověda

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| F1 webový prohlížeč | `Internal` | Určuje, jak nápovědy se zobrazí, pokud chcete vyhledat termín pomocí kombinace kláves Ctrl + F1. Pokud nastavíte hodnotu `Internal`, nápovědy se zobrazí v okně nástroje v sadě Visual Studio. Pokud nastavíte hodnotu `External`, nápovědy se zobrazí ve webovém prohlížeči výchozí. |
| F1 Webové hledaný řetězec | `R site:stackoverflow.com` | Určuje, jak se hledaný text předávají vyhledávací web po stisknutí klávesy Ctrl + F1 na termín, který se v editoru. Ve výchozím nastavení je řetězec `R site:stackoverflow.com`, který připojí `R` pro hledaný termín. `site:stackoverflow.com` Představuje direktivu na vyhledávací web, která říká službě ji k určení rozsahu vyhledávání na stránky v rámci `stackoverflow.com` domény. |
| Prohlížeč nápovědy R | `Automatic` | Ovládací prvky zobrazení nápovědy při hledání v dokumentaci R pomocí F1, `?`, nebo `??`. Pokud nastavíte hodnotu `Automatic`, vykreslí nápovědy v okně vhodné. HTML – Nápověda se například zobrazí v okně nástroje Visual Studio a že se soubory PDF ve výchozím programu PDF. Pokud nastavíte hodnotu `External`, je vykreslen nápovědě ve webovém prohlížeči výchozí. |

### <a name="history"></a>Historie

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Vždy uložit historie | `True` | Určuje, zda RTVS zapisuje do historie příkazů `.RHistory` souboru v pracovním adresáři, vždy, když na projekt je uzavřený. Ukládání historie se stane, i když před ukončení neukládat projektu. |
| Resetování vyhledávací filtr | `True` | Určuje, zda okno Historie můžete filtrovat historie příkazů zobrazit pouze příkazy, které dílčí řetězec odpovídající výraz filtru v dialogovém okně R historie. Toto nastavení určuje, zda chcete resetovat vaše historie vyhledávací filtr vždy, když spusťte nový příkaz nebo přepnout na nový projekt, který aktivuje zatížení jiné `.RHistory` souboru. Výchozí nastavení `True` minimalizuje neočekávaném, když spustíte příkaz s sadu filtrů a zajímat, proč jste spustili příkaz nebyla zobrazena v historii. |
| Pomocí víceřádkovým výběr | `True` | Určuje, zda můžete vybrat více řádků příkazu v historii s jedním kliknutím. Nahoru/dolů navigační šipky v interaktivní systému Windows, taky umožňuje příkazy spíše než řádky. |

### <a name="html"></a>HTML

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Prohlížeč stránky HTML | `External` | Určuje, kde je obsah, jako `ggvis` výkresu, nebo `shiny` aplikace je vykreslen. `Internal`zobrazuje výstup ve formátu HTML v okně nástroje v sadě Visual Studio; `External` zobrazí výstupu protokolu HTML ve výchozím prohlížeči. |

### <a name="logging"></a>protokolování

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Události protokolu | `Normal` | Ovládací prvky podrobností protokolování používá pro RTVS diagnostiky. Výchozí nastavení `Normal` vytvoří soubor protokolu v vaší `TEMP` adresáře. Pokud nastavíte hodnotu `Traffic`, RTVS zaznamená všechny příkazy a odpovědi v relaci. Tyto soubory protokolu se nikdy opustit váš počítač, ale může být užitečné pro diagnostiku problémů v RTVS. |

### <a name="markdown"></a>Markdownu

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Prohlížeče náhled markdownu | `External` | Určuje, kde se zobrazí výstup RMarkdown HTML. `Internal`Zobrazuje dokumentu RMarkdown HTML v okně nástroje v sadě Visual Studio; `External` zobrazí RMarkdown HTML pomocí výchozí prohlížeč. |

### <a name="r-engine"></a>Modul R

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Znakové stránky | `(OS Default)` | Nastaví znaková stránka (národní prostředí) pro R. Ve výchozím nastavení používá základní národní prostředí operačního systému. | 
| CRAN zrcadlení | `(Use .Rprofile)` | Nastaví výchozí CRAN zrcadlení pro instalace balíčku. Výchozí nastavení `Use .Rprofile` respektuje CRAN zrcadlení nastavení ve vaší `.RProfile` souboru. |

### <a name="workspace"></a>Pracovní prostor

| Možnost | Výchozí hodnota | Popis |
| --- | --- | --- |
| Načtení pracovního prostoru po otevření projektu | `No` | Nastavení na `Yes` umožňuje načítání dat relace z `.RData` souboru do globální prostředí při otevření projektu. |
| Zobrazit výzvu k uložení prostoru na resetování | `Yes` | Nastavení na `No` zakáže ukládání pracovního prostoru, když kliknete na tlačítko Obnovit v okně interaktivní výzvy. |
| Uložení pracovního prostoru po zavření projektu | `No` | Nastavení na `Yes` umožňuje ukládání globální prostředí tak, aby `.RData` souboru při zavření projektu. |
| Zobrazit dialogové okno před přepnutím pracovních prostorů | `Yes` | Nastavení na `No` zakáže výzvy pro uživatele k potvrzení při přepínání mezi jiné pracovní prostory. V tématu [přepínání mezi pracovních prostorů](workspaces.md#switching-between-workspaces) |
| Zobrazit počítače zatížení indikátoru | `False` | Určuje, zda se indikátor zatížení procesoru a paměti nebo síťových ve stavovém řádku. Protože indikátoru způsobuje síťový provoz, je užitečné k tomu `False` ve vzdálené měřené scénáře. Změna tato možnost vyžaduje restartování sady Visual Studio. |
