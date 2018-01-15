---
title: "Rychlé akce | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload: multiple
ms.openlocfilehash: 259e033aa32caaca59f37d7dc77ac095b4709878
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="quick-actions"></a>Rychlé akce

Rychlé akce vám umožní snadno refactor, generovat nebo jinak změnit kód, který představuje jednu akci. Rychlé akce jsou k dispozici pro jazyk C#, [C++](/cpp/ide/writing-and-refactoring-code-cpp)a soubory s kódem jazyka Visual Basic. Některé akce jsou specifické pro jazyk a jiné jenom pro všechny jazyky.

Můžete použít rychlé akce pomocí ikonou žárovky ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png), nebo stisknutím kombinace kláves **Ctrl**+**.** Pokud je ukazatelem na příslušný řádek kódu. Uvidíte, že žárovky je červenou vlnovkou a Visual Studio má návrhy pro informace o vyřešení problému. Například pokud máte chybu označená červenou vlnovkou, žárovky se zobrazí, když jsou k dispozici pro tuto chybu opravy.

Pro žádný jazyk třetím stranám můžete zadat vlastní diagnostiky a návrhy, například jako součást sady SDK a Visual Studio žárovek bude light podle těchto pravidel.

## <a name="to-see-a-light-bulb"></a>Chcete-li zobrazit žárovky

1. V mnoha případech žárovek samovolně zobrazit při přesunutí ukazatele myši v místě chybu nebo na levém okraji editoru při přesunout znak v souladu, který v něm došlo k chybě. Až uvidíte červenou vlnovkou, můžete zobrazit žárovky myší. Může také způsobit žárovky zobrazíte při použití myši a klávesnice pro přejděte na libovolné místo v řádku vyskytl problém.

1. Stiskněte klávesu **Ctrl**+**.** kdekoli na řádek pro vyvolání žárovky a přejít přímo na seznam potenciálních opravy.

   ![Žárovky s ukazatele myši](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")

## <a name="to-see-potential-fixes"></a>Chcete-li zobrazit potenciální opravy

Buď klikněte na šipku dolů, nebo zobrazit potenciální opravy odkaz zobrazíte seznam rychlé akce, které pro vás může trvat žárovky.

![Žárovky rozšířit](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="see-also"></a>Viz také

[Generování kódu v sadě Visual Studio](../ide/code-generation-in-visual-studio.md)  
[Běžné rychlé akce](../ide/common-quick-actions.md)  
[Styly kódu a rychlé akce](../ide/code-styles-and-quick-actions.md)  
[Psaní a refaktoring kódu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)