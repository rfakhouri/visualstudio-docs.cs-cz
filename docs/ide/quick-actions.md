---
title: Rychlá akce, návrhy a šroubováky
ms.date: 03/28/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1a08e54025ac0826b88a3d3fcee299beef245d13
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62811982"
---
# <a name="quick-actions"></a>Rychlé akce

Rychlé akce vám umožní snadno Refaktorujte, generovat nebo jinak upravit kód pomocí jedné akce. Rychlé akce jsou k dispozici pro C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp)a soubory kódu jazyka Visual Basic. Některé akce jsou specifické pro jazyk a jiné jenom pro všechny jazyky.

Rychlé akce umožňuje:

- Použít opravu kódu [code analyzer](../code-quality/roslyn-analyzers-overview.md) porušení pravidla

- [Potlačit](../code-quality/use-roslyn-analyzers.md#suppress-violations) porušení pravidla analyzátor kódu

- Použít refaktoring (například [vložená dočasná proměnná](../ide/reference/inline-temporary-variable.md))

- Generování kódu (například [zavést lokální proměnnou](../ide/reference/introduce-local-variable.md))

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [refaktoringu (Visual Studio for Mac)](/visualstudio/mac/refactoring).

Rychlé akce lze použít pomocí žárovky ![ikonou žárovky](media/light-bulb-icon.png) nebo šroubovák ![šroubovák ikonu](media/screwdriver-icon.png) ikony, nebo stisknutím klávesy **Ctrl** + **.** Když je kurzor na řádek kódu, pro který je k dispozici akci. Zobrazí se žárovka chyba ![ikonu žárovky chyby](media/error-light-bulb-icon.png) pokud existuje červená vlnovka udávající chybu a sady Visual Studio je k dispozici pro tuto chybu opravu.

Pro libovolný jazyk třetím stranám poskytnete vlastní Diagnostika a návrhy, například jako součást sady SDK a návrhy sady Visual Studio se zobrazí podle těchto pravidel.

## <a name="icons"></a>Ikony

Ikona, která se zobrazí, když je k dispozici je rychlá akce obsahuje údaj o typu opravu, nebo refaktoring, který je k dispozici. *Šroubovák* ![šroubovák ikonu](media/screwdriver-icon.png) ikona značí pouze, že nejsou k dispozici pro kód změnit akce, ale byste je neměli používat nemusí. *Žlutá žárovka* ![ikonou žárovky](media/light-bulb-icon.png) ikona značí, že jsou k dispozici akce, které jste *by měl* proveďte ke zlepšení kódu. *Chyba žárovky* ![ikonou žárovky chyba](media/error-light-bulb-icon.png) ikona značí, že je k dispozici akci, která řeší chybu v kódu.

## <a name="to-see-a-light-bulb-or-screwdriver"></a>Pokud chcete zobrazit návrhy nebo šroubovák

Pokud opravu je dostupná, zobrazí se návrhy:

- Při přesunutí ukazatele myši v místě chybu

   ![Žárovka s najede myší](../ide/media/vs2015_lightbulb_hover.png)

- Do levého okraje editoru při přesunutí blikající kurzor (ukazatel) na příslušný řádek kódu

Můžete také stisknout klávesu **Ctrl**+**.** kdekoli v řádku zobrazíte seznam dostupných rychlé akce a refaktoringy.

Pokud chcete zobrazit možné opravy, vyberte buď na šipku dolů vedle žárovky nebo **ukazují možné opravy** odkaz. Zobrazí se seznam dostupné rychlé akce.

![Žárovka rozšířit](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu v sadě Visual Studio](../ide/code-generation-in-visual-studio.md)
- [Běžné rychlé akce](../ide/common-quick-actions.md)
- [Styly kódu a rychlé akce](../ide/code-styles-and-quick-actions.md)
- [Zápis a Refaktorujte kód (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
- [Refaktoring (Visual Studio for Mac)](/visualstudio/mac/refactoring)