---
title: 'Postupy: Nastavení vlastností analýzy kódu pro projekty C/C++'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.native
- VC.Project.VCCLCompilerTool.EnablePrefast
- VC.Project.VCFxCopTool.EnablePREfast
- VC.Project.VCFxCopTool.IgnoreGeneratedCode
helpviewer_keywords:
- properties, C/C++ Code Analysis
- properties, Code Analysis
- code analysis properties
- C/C++ code analysis properties
ms.assetid: 7af52097-6d44-4785-9b9f-43b7a7d447d7
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 72866618383382389ad5e5706ae2a0999c89c346
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923990"
---
# <a name="how-to-set-code-analysis-properties-for-cc-projects"></a>Postupy: Nastavení vlastností analýzy kódu pro projekty C/C++
Můžete nakonfigurovat, která pravidla Nástroj pro analýzu kódu používá pro analýzu kódu v každé konfiguraci projektu. Kromě toho můžete směrovat analýzu kódu pro potlačení upozornění z kódu, který byl vygenerován a přidán do projektu nástrojem třetí strany.

## <a name="code-analysis-property-page"></a>Stránka vlastností analýzy kódu
Stránka vlastností **Analýza kódu** obsahuje všechna nastavení konfigurace analýzy kódu pro projekt. Chcete-li otevřít stránku vlastností analýzy kódu pro projekt v **Průzkumník řešení**, klikněte pravým tlačítkem myši na projekt a potom klikněte na příkaz **vlastnosti**. Dále rozbalte položku **Vlastnosti konfigurace** a vyberte kartu **Analýza kódu** .

## <a name="project-configuration-and-platform"></a>Konfigurace a platforma projektu
Seznam **konfigurací** a seznam **platforem** umožňuje použít různá nastavení analýzy kódu pro různé konfigurace projektu a kombinace platforem. Například můžete směrovat analýzu kódu a použít jednu sadu pravidel pro projekt pro sestavení pro ladění a jinou sadu pro sestavení vydaných verzí.

## <a name="enabling-code-analysis"></a>Povolení analýzy kódu
Můžete se rozhodnout, jestli chcete pro svůj projekt povolit analýzu kódu, a to tak, že vyberete **možnost povolit analýzu kódu pro sestavení C/C++ on**. V kombinaci se seznamem **konfigurací** můžete například rozhodnout zakázat analýzu kódu pro sestavení ladění a povolit ji pro sestavení vydaných verzí.

Pokud projekt obsahuje spravovaný kód, můžete rozhodnout, zda chcete povolit nebo zakázat analýzu kódu výběrem možnosti **Povolit analýzu kódu při sestavení**.

Analýza kódu je navržena tak, aby vám pomohla zlepšit kvalitu kódu a vyhnout se běžným nástrah. Proto pečlivě zvažte, zda chcete zakázat analýzu kódu. Obvykle je lepší zakázat sady pravidel nebo jednotlivá pravidla, která nechcete použít pro váš projekt.

## <a name="generated-code"></a>Generovaný kód
Vývojáři často používají nástroje k rychlému vývoji aplikací. Tyto nástroje mohou vygenerovat kód, který je přidán do projektu. Je možné, že budete chtít zobrazit porušení pravidel, která analýza kódu zjistí v generovaném kódu. Můžete je však nechtít zobrazit, pokud nechcete kód zachovat.

Zaškrtávací políčko **Potlačit výsledky z vygenerovaného kódu** na stránce **Obecné** vlastnosti umožňuje vybrat, zda chcete zobrazit upozornění analýzy kódu ze spravovaného kódu, který je generován nástrojem třetí strany.

## <a name="rule-sets"></a>Sady pravidel
Pokud projekt obsahuje spravovaný kód, můžete vybrat pravidla, která se mají použít při analýze kódu výběrem sady pravidel ze seznamu **Spustit sadu pravidel** .

## <a name="see-also"></a>Viz také

- [Analýza kvality spravovaného kódu](../code-quality/code-analysis-for-managed-code-overview.md)
- [Upozornění Analýzy kódu pro C/C++](../code-quality/code-analysis-for-c-cpp-warnings.md)