---
title: Nastaví pravidel nástroje Analýza kódu v sadě Visual Studio
ms.date: 04/02/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a445aecdd5a9f02bca8d43e42646c991742a626
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>Sad použití pravidel k seskupování pravidel analýzy kódu

Když konfigurujete analýza kódu v sadě Visual Studio, můžete ze seznamu předdefinovaných *sad pravidel*. Sada pravidel platí pro projekt a je seskupení kódu pravidel analýzy, které identifikují cílové problémy a konkrétní podmínky pro tento projekt. Například můžete použít sadu pravidel, která je určená pro hledání kódu veřejně dostupné rozhraní API, nebo jen minimální doporučená pravidla. Můžete také použít sadu pravidel, která zahrnuje všechna pravidla.

Můžete přizpůsobit sadu přidání nebo odstranění pravidla nebo změna závažnosti pravidlo vypadaly jako varování nebo chyby pravidel **seznam chyb**. Sada vlastních pravidel může splnit potřebu konkrétního vývojového prostředí. Při přizpůsobování sadu pravidel, poskytuje editor sad pravidel vyhledávání a filtrování nástrojů, které vám pomůžou v procesu.

## <a name="rule-set-format"></a>Formát sady pravidel

Sada pravidel je zadána ve formátu XML *analýza* souboru. Pravidla, které se skládají z ID a *akce*, jsou seskupené podle ID analyzátor a obor názvů v souboru.

Obsah XML *analýza* soubor vypadá podobně jako tento:

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> Aby bylo jednodušší [upravit sadu pravidel](../code-quality/working-in-the-code-analysis-rule-set-editor.md) v grafickém **Editor nastavit pravidla** než ručně.

Pravidlo nastavené pro projekt je zadána `CodeAnalysisRuleSet` vlastnost v souboru projektu sady Visual Studio. Příklad:

```xml
<CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
```

## <a name="see-also"></a>Viz také

- [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/rule-set-reference.md)
