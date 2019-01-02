---
title: 'Postupy: Nastavení vlastností analýzy kódu pro projekty C/C++'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 000b731bffe6b2fe02e34e98ebfd3ce8a21f5bd8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915627"
---
# <a name="how-to-set-code-analysis-properties-for-cc-projects"></a>Postupy: Nastavení vlastností analýzy kódu pro projekty C/C++
Můžete nakonfigurovat pravidla, která používá nástroj pro analýzu kódu pro analýzu kódu v každé konfiguraci projektu. Kromě toho může směrovat analýzy kódu pro potlačení varování z kódu, které se generují a přidávají do svého projektu pomocí nástroje třetích stran.

## <a name="code-analysis-property-page"></a>Stránka vlastností analýzy kódu
 **Analýzy kódu** stránka vlastností obsahuje všechna nastavení konfigurace analýzy kódu pro projekt. Otevřete stránku vlastnosti analýzy kódu pro projekt v **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti**. Dále rozbalte **vlastnosti konfigurace** a vyberte **analýzy kódu** kartu.

## <a name="project-configuration-and-platform"></a>Konfigurace projektu a platformy
 **Konfigurace** seznamu a **platformy** seznamu umožňuje použít nastavení analýzy kódu pro různé kombinace konfigurace a platforma jiného projektu. Můžete například nasměrovat sestavení analýzy kódu, které chcete použít jednu sadu pravidel pro váš projekt pro ladění a jiné sady pro verzi sestavení.

## <a name="enabling-code-analysis"></a>Povolení analýzy kódu
 Můžete se rozhodnout, jestli se má povolit analýzu kódu pro váš projekt tak, že vyberete **povolit kód analýzy pro C/C++ při sestavení**. V kombinaci s **konfigurace** seznamu, můžete je například rozhodnete zákaz analýzy kódu pro sestavení pro ladění a povolit ho pro verzi sestavení.

 Pokud váš projekt obsahuje spravovaný kód, můžete se rozhodnout, jestli se má povolit nebo zakázat analýzy kódu tak, že vyberete **povolit analýzu kódu na sestavení**.

 Analýza kódu slouží k mohli vylepšit kvalitu kódu a vyhnout běžným nástrahám. Proto je třeba pečlivě zvážit, zda chcete zakázat analýzy kódu. Je obvykle vhodnější zakázat sady pravidel nebo jednotlivá pravidla, které nechcete použít pro váš projekt.

## <a name="generated-code"></a>Generovaný kód
 Vývojáři často pomocí nástroje vám pomůžou s vývojem aplikací rychle. Tyto nástroje můžete vygenerovat kód, který je přidán do projektu. Můžete chtít zobrazit porušení pravidel, které zjistí analýzy kódu v generovaném kódu. Ale nebudete chtít vidět, pokud nechcete zachovat kód.

 **Potlačit výsledky z kód generovaný** zaškrtávací políčko na **Obecné** stránku vlastností lze vybrat, jestli chcete zobrazit upozornění analýzy kódu ze spravovaného kódu, který je vygenerován pomocí nástroje třetích stran .

## <a name="rule-sets"></a>Sady pravidel
 Pokud váš projekt obsahuje spravovaný kód, můžete si vybrat pravidla se použijí při analýze kódu tak, že vyberete sadu z pravidel **spustit tuto sadu pravidel** seznamu.

## <a name="see-also"></a>Viz také

- [Analýza kvality spravovaného kódu](../code-quality/code-analysis-for-managed-code-overview.md)
- [Upozornění Analýzy kódu pro C/C++](../code-quality/code-analysis-for-c-cpp-warnings.md)