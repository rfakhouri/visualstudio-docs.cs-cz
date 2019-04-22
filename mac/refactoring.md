---
title: Refaktoring kódu
description: Ladění kódu pomocí sady Visual Studio pro Mac a rychlé akce.
author: conceptdev
ms.author: crdun
ms.date: 03/29/2019
ms.assetid: C7782BF3-016F-4B41-8A81-85FC540A1A8F
ms.custom: video
ms.openlocfilehash: 48e290fddd1c4b7c95ac5e76cb6cf5908247e6f6
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "58856512"
---
# <a name="refactoring"></a>Refaktoring

Refaktoring kódu je způsob, jak změnit uspořádání, struktury a vysvětlení existující kód, zatímco je zajištěna, která se nemění celkový chování kódu.

Refaktoring vytváří znamenala základ kódu, takže použitelný, čitelný a udržovatelný pro vás nebo jakékoli jiné vývojáře nebo uživatel, který může odkazovat na kód.

Visual Studio pro Mac integrace roslyn společnosti Microsoft open-source platformy kompilátoru .NET, umožňuje více operací refaktoringu.

## <a name="renaming"></a>Přejmenování

*Přejmenovat* refaktoring příkaz lze použít na libovolný identifikátor kódu (například název třídy, název vlastnosti atd.) a vyhledejte všechny výskyty daného identifikátoru je změnit. Přejmenování symbolu, klepněte na něj pravým tlačítkem myši a zvolte **přejmenování...** , nebo použijte **Cmd (⌘) + R** vazba klíče:

![Přejmenování položky nabídky](media/refactoring-renaming1.png)

To klade důraz na symbol a všechny odkazy na něj. Když spustíte zadáním nového názvu se automaticky změní všechny odkazy ve vašem kódu a změny můžete potvrzovat stisknutím kombinace kláves **Enter**:

![Přejmenování a identifikátor](media/refactoring-renaming2.png)

## <a name="quick-actions"></a>Rychlé akce

Rychlé akce vám umožní snadno Refaktorujte, generovat nebo jinak upravit kód pomocí jedné akce.

Rychlé akce umožňuje:

* Použít opravu kódu pro porušení pravidel analyzátor kódu
* Potlačit porušení pravidla analyzátor kódu
* Použít refaktoring (například vložená dočasná proměnná)
* Generování kódu (například přidání místní proměnné)

Rychlé akce lze použít pomocí žárovky ![ikonou žárovky](media/quick-actions-light-bulb-icon.png) nebo šroubovák ![šroubovák ikonu](media/quick-actions-screwdriver-icon.png) ikony, nebo stisknutím klávesy **možnost (⌥)** +  **Zadejte** když je kurzor na řádek kódu, pro který je k dispozici akci. Zobrazí se žárovka chyba ![ikonu žárovky chyby](media/quick-actions-error-light-bulb-icon.png) pokud existuje červená vlnovka udávající chybu a sady Visual Studio je k dispozici pro tuto chybu opravu.

Pro libovolný jazyk třetím stranám poskytnete vlastní Diagnostika a návrhy, například jako součást sady SDK a sady Visual Studio návrhy bylo možné na základě těchto pravidel.

### <a name="quick-action-icons"></a>Rychlé akce ikony
Ikona, která se zobrazí, když je k dispozici je rychlá akce obsahuje údaj o typu opravu, nebo refaktoring, který je k dispozici. *Šroubovák* ![šroubovák ikonu](media/quick-actions-screwdriver-icon.png) ikona značí pouze, že nejsou k dispozici pro kód změnit akce, ale byste je neměli používat nemusí. *Žlutá žárovka* ![ikonou žárovky](media/quick-actions-light-bulb-icon.png) ikona značí, že jsou k dispozici akce, které jste *by měl* proveďte ke zlepšení kódu. *Chyba žárovky* ![ikonou žárovky chyba](media/quick-actions-error-light-bulb-icon.png) ikona značí, že je k dispozici akci, která řeší chybu v kódu.

### <a name="to-see-a-light-bulb-or-screwdriver"></a>Pokud chcete zobrazit návrhy nebo šroubovák

- Pokud je k dispozici oprava, návrhy samovolně se zobrazí při najetí myší na umístění k chybě.

   ![Žárovka s najede myší](media/refactoring-lightbulb-hover.png)

- Ikony žárovky šroubováky zobrazí a do levého okraje editoru při přesunutí blikající kurzor do jediného řádku kódu, pro který je k dispozici rychle reagovat.

- Stisknutím klávesy **možnost (⌥)**+**Enter** kdekoli na řádek zobrazíte seznam dostupných rychlé akce a refaktoringy.

![Zobrazit kontext položky](media/refactoring-context-action.png)

Najetí myší nad kontext akce, které poskytuje náhled co budou přidány nebo odstraněny z vašeho kódu.

![Možnost zadat místní položky](media/refactoring-image2a.png)

Pokud chcete povolit tyto možnosti, musíte vybrat *povolit zdrojovou analýzu otevřených souborů* v možnostech **Visual Studio for Mac > Předvolby > textový Editor > zdrojová analýza**:

![Povolení zdrojová analýza](media/refactoring-options.png)

Existuje více než 100 možných akcí, které mohou být navržena, které jsou povolené nebo zakázané tak, že přejdete do **Visual Studio for Mac > Předvolby > zdrojová analýza > C# > Akce kódu** a výběr nebo unselecting políčko vedle položky akce:

![Zdrojová analýza C# akce](media/refactoring-image3a.png)

### <a name="common-quick-actions"></a>Běžné rychlé akce

Další informace o běžné rychlé akce v [běžné rychlé akce](/visualstudio/ide/common-quick-actions) článku.

## <a name="source-analysis"></a>Zdrojová analýza

Zdrojová analýza analyzuje podtržení potenciální chyby a porušení stylu kódu v reálném čase a poskytuje automatické opravy jako kontext akce.

Můžete zobrazit všechny výsledky analýzy zdroje pro jakýkoli soubor v okamžiku, zobrazením posuvníku na pravé straně textového editoru:

![Boční panel analýzy zdroje](media/refactoring-image4a.png)

Pokud kliknete na kolečko v horní části, můžete iterovat každý návrh s nejvyšší závažností problémy zobrazeno prvních. Problém můžete vyřešit pomocí kontextu akce najede myší jednotlivé výsledek nebo řádek zobrazí:

![Zdrojová položka analýzy](media/refactoring-image5.png)

## <a name="related-video"></a>Související videa

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Refactoring-Code/player]

## <a name="see-also"></a>Viz také:

- [Rychlé akce (Visual Studio na Windows)](/visualstudio/ide/quick-actions)
- [Refaktorování kódu (Visual Studio na Windows)](/visualstudio/ide/refactoring-in-visual-studio)