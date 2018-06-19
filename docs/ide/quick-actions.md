---
title: Rychlé akce, žárovek a šroubováky
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
ms.openlocfilehash: d413d5b440c39c3603e1e909fb0c4645719f188b
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
ms.locfileid: "34064847"
---
# <a name="quick-actions"></a>Rychlé akce

Rychlé akce vám umožní snadno refactor, generovat nebo jinak změnit kód, který představuje jednu akci. Rychlé akce jsou k dispozici pro jazyk C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp)a soubory s kódem jazyka Visual Basic. Některé akce jsou specifické pro jazyk a jiné jenom pro všechny jazyky.

Rychlé akce umožňuje:

- použít oprava kódu [code analyzátor](../code-quality/roslyn-analyzers-overview.md) pravidlo porušení
- [Potlačit](../code-quality/use-roslyn-analyzers.md) porušení pravidlo analyzátor kódu
- použít refaktoring (například [vložené dočasnou proměnnou](../ide/reference/inline-temporary-variable.md))
- generování kódu (například [zavést místní proměnné](../ide/reference/introduce-local-variable.md))

Můžete použít rychlé akce pomocí žárovky ![ikonou žárovky](media/light-bulb-icon.png) nebo šroubovák ![šroubovák ikonu](media/screwdriver-icon.png) ikony, nebo stisknutím kombinace kláves **Ctrl** + **.** Pokud je ukazatelem na řádek kódu, pro který je k dispozici. Uvidíte žárovky k chybě ![ikonou žárovky chyba](media/error-light-bulb-icon.png) Pokud je červenou vlnovkou indikující chybu a má pro tuto chybu k dispozici oprava Visual Studio.

Pro žádný jazyk třetím stranám můžete zadat vlastní diagnostiky a návrhy, například jako součást sady SDK a Visual Studio žárovek light na základě těchto pravidel.

## <a name="icons"></a>Ikony

Ikona, která se zobrazí, když je k dispozici rychlé akce indikuje typ oprava nebo refaktoring, který je k dispozici. *Šroubovák* ![šroubovák ikonu](media/screwdriver-icon.png) ikona označuje pouze akce, které jsou k dispozici pro změnit kód, že byste neměli používat nutně je. *Žárovky žlutý* ![ikonou žárovky](media/light-bulb-icon.png) ikona označující, nejsou k dispozici akce, které *by měl* proveďte k vylepšení vašeho kódu. *Chyba žárovky* ![ikonou žárovky chyba](media/error-light-bulb-icon.png) ikona označuje, že je k dispozici akci, která řeší chybu v kódu.

## <a name="to-see-a-light-bulb-or-screwdriver"></a>Chcete-li zobrazit žárovky nebo šroubovák

- Pokud oprava je k dispozici, žárovek samovolně se při přesunutí ukazatele myši v umístění k chybě.

   ![Žárovky s ukazatele myši](../ide/media/vs2015_lightbulb_hover.png)

- Žárovek a šroubováky při přesunout znak do řádek kódu, pro který je k dispozici rychlé akce zobrazují na levém okraji editoru.

- Stiskněte klávesu **Ctrl**+**.** kdekoli na řádku zobrazíte seznam dostupných rychlé akce a refaktoring.

## <a name="to-see-potential-fixes"></a>Chcete-li zobrazit potenciální opravy

Vyberte buď na šipku dolů vedle žárovky nebo **zobrazit potenciální opravy** odkaz zobrazíte seznam rychlé akce, které jsou k dispozici.

![Žárovky rozšířit](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>Viz také

- [Generování kódu v sadě Visual Studio](../ide/code-generation-in-visual-studio.md)
- [Běžné rychlé akce](../ide/common-quick-actions.md)
- [Styly kódu a rychlé akce](../ide/code-styles-and-quick-actions.md)
- [Zápis a refactor kódu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)