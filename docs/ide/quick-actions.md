---
title: Rychlé akce
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 90ec61924a9a08fc01c54f04bd8a7cc82fcc9525
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="quick-actions"></a>Rychlé akce

Rychlé akce vám umožní snadno refactor, generovat nebo jinak změnit kód, který představuje jednu akci. Rychlé akce jsou k dispozici pro jazyk C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp)a soubory s kódem jazyka Visual Basic. Některé akce jsou specifické pro jazyk a jiné jenom pro všechny jazyky.

Rychlé akce umožňuje:

- použít oprava kódu [code analyzátor](../code-quality/roslyn-analyzers-overview.md) pravidlo porušení
- [Potlačit](../code-quality/use-roslyn-analyzers.md) porušení pravidlo analyzátor kódu
- použít refaktoring (například [vložené dočasnou proměnnou](../ide/reference/inline-temporary-variable.md))
- generování kódu (například [zavést místní proměnné](../ide/reference/introduce-local-variable.md))

Můžete použít rychlé akce pomocí ikonou žárovky ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png), nebo stisknutím kombinace kláves **Ctrl**+**.** Pokud je ukazatelem na řádek kódu, pro který je k dispozici. Uvidíte, že žárovky je červenou vlnovkou a Visual Studio má návrhy pro informace o vyřešení problému. Například pokud máte chybu označená červenou vlnovkou, žárovky se zobrazí, když jsou k dispozici pro tuto chybu opravy.

Pro žádný jazyk třetím stranám můžete zadat vlastní diagnostiky a návrhy, například jako součást sady SDK a Visual Studio žárovek light na základě těchto pravidel.

## <a name="to-see-a-light-bulb"></a>Chcete-li zobrazit žárovky

1. V mnoha případech žárovek samovolně zobrazit při přesunutí ukazatele myši v místě chybu nebo na levém okraji editoru při přesunout znak v souladu, který obsahuje chybu. Až uvidíte červenou vlnovkou, můžete zobrazit žárovky myší. Může také způsobit žárovky zobrazíte při použití myši a klávesnice pro přejděte na libovolné místo v řádku vyskytl problém.

1. Stiskněte klávesu **Ctrl**+**.** kdekoli na řádek pro vyvolání žárovky a přejít přímo na seznam potenciálních opravy.

   ![Žárovky s ukazatele myši](../ide/media/vs2015_lightbulb_hover.png)

## <a name="to-see-potential-fixes"></a>Chcete-li zobrazit potenciální opravy

Buď klikněte na šipku dolů nebo **zobrazit potenciální opravy** odkaz zobrazíte seznam rychlé akce, které pro vás může trvat žárovky.

![Žárovky rozšířit](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>Viz také

- [Generování kódu v sadě Visual Studio](../ide/code-generation-in-visual-studio.md)
- [Běžné rychlé akce](../ide/common-quick-actions.md)
- [Styly kódu a rychlé akce](../ide/code-styles-and-quick-actions.md)
- [Zápis a refactor kódu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)