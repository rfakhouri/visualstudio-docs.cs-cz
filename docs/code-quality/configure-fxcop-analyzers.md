---
title: Konfigurace analyzátory FxCop pomocí editorconfig
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- FxCop analyzers, configuring
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ac751b7ec130b6bfbb18752c02b491b6c342f172
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57875089"
---
# <a name="configure-fxcop-analyzers"></a>Konfigurace analyzátory FxCop

[Analyzátory FxCop](install-fxcop-analyzers.md) skládat z vašich nejdůležitějších "FxCop" pravidla ze statické analýzy kódu, převést na analyzátory Roslyn. Analyzátory FxCop kódu můžete nakonfigurovat dvěma způsoby:

- S [sada pravidel, která](#fxcop-analyzer-rule-sets), který umožňuje povolit nebo zakázat pravidlo a nastavit závažnost jednotlivých pravidel narušení.

- Počínaje verzí 2.6.3 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) balíček NuGet, prostřednictvím [souboru .editorconfig](#editorconfig-file). [Konfigurovatelných možností, které](fxcop-analyzer-options.md) let, můžete upřesnit, které části vašeho základu kódu k analýze.

> [!TIP]
> Informace o rozdílech mezi FxCop statickou analýzu kódu a analyzátory FxCop, naleznete v tématu [analyzátory FxCop – nejčastější dotazy](fxcop-analyzers-faq.md).

## <a name="fxcop-analyzer-rule-sets"></a>Sady pravidel FxCop analyzátoru

Jedním ze způsobů konfigurace analyzátory FxCop je pomocí XML *sada pravidel, která*. Sada pravidel je seskupení pravidel analýzy kódu, které vyhledávají cílené problémy a zvláštní podmínky. Sady pravidel umožňují povolit nebo zakázat pravidlo a nastavit závažnost jednotlivých pravidel narušení.

Balíček NuGet analyzátor FxCop obsahuje sady předdefinovaných pravidel pro následujících kategorií pravidel:

- návrh
- dokumentace
- udržovatelnosti
- pojmenování
- výkon
- spolehlivost
- zabezpečení
- využití

Další informace najdete v tématu [sady pravidel pro analyzátory Roslyn](analyzer-rule-sets.md).

## <a name="editorconfig-file"></a>EditorConfig souboru

Pravidla analyzátoru můžete nakonfigurovat tak, že přidáte páry klíč hodnota do [.editorconfig](https://editorconfig.org) souboru. Konfigurační soubor může být [specifické pro projekt](#per-project-configuration) nebo to může být [sdílené](#shared-configuration) mezi dva nebo více projektů.

### <a name="per-project-configuration"></a>Konfigurace projektů

Chcete-li povolit na základě .editorconfig analyzátoru konfigurace pro konkrétní projekt, přidejte *.editorconfig* souboru do kořenového adresáře projektu.

> [!TIP]
> Souboru .editorconfig můžete přidat do projektu kliknutím pravým tlačítkem myši na projekt v **Průzkumníka řešení** a vyberete **přidat** > **nová položka**. V **přidat novou položku** okno, zadejte **editorconfig** do vyhledávacího pole. Vyberte **editorconfig souboru (výchozí)** šablony a zvolte **přidat**.
>
> ![Přidání editorconfig položky do projektu v sadě Visual Studio](media/add-editorconfig-file.png)

V současné době neexistuje žádná podpora hierarchické "kombinování".editorconfig souborů, které existují na úrovních jiný adresář, například úroveň řešení a projektu.

### <a name="shared-configuration"></a>Sdílená konfigurace

Můžete sdílet soubor .editorconfig pro analyzátor konfigurace mezi dvěma nebo více projektů, ale vyžaduje další kroky.

1. Uložit *.editorconfig* do společného umístění.

2. Vytvoření *.props* soubor s následujícím obsahem:

   ```xml
   <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <PropertyGroup>
       <SkipDefaultEditorConfigAsAdditionalFile>true</SkipDefaultEditorConfigAsAdditionalFile>
     </PropertyGroup>
     <ItemGroup Condition="Exists('<your path>\.editorconfig')" >
       <AdditionalFiles Include="<your path>\.editorconfig" />
     </ItemGroup>
   </Project>
   ```

3. Přidejte řádek, který vaše *.csproj* nebo *.vbproj* soubor k importu *.props* souboru, kterou jste vytvořili v předchozím kroku. Tento řádek musí být umístěna před všechny řádky, které importují analyzátor FxCop *.props* soubory. Například, pokud je název souboru .props *editorconfig.props*:

   ```xml
   ...
   <Import Project="..\..\editorconfig.props" Condition="Exists('..\..\editorconfig.props')" />
   <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
   ...
   ```

4. Znovu načte projekt.

> [!NOTE]
> Starší pravidla FxCop (statické analýzy kódu FxCop) nelze konfigurovat pomocí souboru .editorconfig.

## <a name="option-scopes"></a>Možnost obory

Každou možnost lze konfigurovat pro všechna pravidla, kategorie pravidla (třeba zásady vytváření názvů nebo návrh) nebo konkrétní pravidlo.

### <a name="all-rules"></a>Všechna pravidla

Syntaxe pro možnost pro všechna pravidla konfigurace vypadá takto:

|Syntaxe|Příklad|
|-|-|
| dotnet_code_quality.OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>Kategorie pravidel

Syntaxe pro možnost pro konfiguraci *kategorie* pravidel (například názvy, návrhu nebo výkon) je následující:

|Syntaxe|Příklad|
|-|-|
| dotnet_code_quality.RuleCategory.OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>Konkrétní pravidla

Konfigurace možnost pro konkrétní pravidlo syntaxe vypadá takto:

|Syntaxe|Příklad|
|-|-|
| dotnet_code_quality.RuleId.OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="see-also"></a>Viz také:

- [Analyzátor konfigurace](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [Analyzátory FxCop](install-fxcop-analyzers.md)
