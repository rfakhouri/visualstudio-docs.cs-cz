---
title: Konfigurace analyzátorů FxCop pomocí editorconfig
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- FxCop analyzers, configuring
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 68c175a55c9e60e870a5466a831aaae50d62dced
ms.sourcegitcommit: 9c07ae6fb18204ea080c8248994a683fa12e5c82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2019
ms.locfileid: "70293452"
---
# <a name="configure-fxcop-analyzers"></a>Konfigurace analyzátorů FxCop

[Analyzátory FxCop](install-fxcop-analyzers.md) se skládají z nejdůležitějších pravidel "FxCop" z analyzátoru starší verze, která se převedou na analyzátory kódu založené na .NET Compiler Platform. Analyzátory kódu FxCop můžete nakonfigurovat dvěma způsoby:

- Se [sadou pravidel](#fxcop-analyzer-rule-sets), která umožňuje povolit nebo zakázat pravidlo a nastavit závažnost pro porušení jednotlivých pravidel.

- Počínaje verzí 2.6.3 balíčku NuGet [Microsoft. CodeAnalysis. FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) prostřednictvím [souboru. editorconfig](#editorconfig-file). [Konfigurovatelné možnosti](fxcop-analyzer-options.md) umožňují Upřesnit, které části základu kódu se mají analyzovat.

> [!TIP]
> Informace o rozdílech mezi staršími analyzátory analýz a FxCop najdete v tématu [Nejčastější dotazy k analyzátorům FxCop](fxcop-analyzers-faq.md).

## <a name="fxcop-analyzer-rule-sets"></a>Sady pravidel nástroje FxCop Analyzer

Jedním ze způsobů, jak nakonfigurovat analyzátory FxCop, je použití *sady pravidel*XML. Sada pravidel je seskupení pravidel analýzy kódu, která identifikují cílené problémy a konkrétní podmínky. Sady pravidel umožňují povolit nebo zakázat pravidlo a nastavit závažnost pro porušení jednotlivých pravidel.

Balíček NuGet pro FxCop Analyzer obsahuje předdefinované sady pravidel pro následující kategorie pravidel:

- návrh
- dokumentace
- udržovatelnosti
- pojmenování
- výkon
- spolehlivost
- zabezpečení
- využití

Další informace najdete v tématu [sady pravidel pro analyzátory kódu](analyzer-rule-sets.md).

## <a name="editorconfig-file"></a>Soubor EditorConfig

Pravidla nástroje FxCop Analyzer můžete nakonfigurovat přidáním párů klíč-hodnota do souboru [. editorconfig](https://editorconfig.org) . Konfigurační soubor může být [specifický pro projekt](#per-project-configuration) nebo může být [sdílen](#shared-configuration) mezi dvěma nebo více projekty.

> [!NOTE]
> Starší pravidla FxCop nejde nakonfigurovat pomocí souboru. editorconfig.

### <a name="per-project-configuration"></a>Konfigurace pro jednotlivé projekty

Chcete-li povolit konfiguraci analyzátoru založeného na editorconfig pro konkrétní projekt, přidejte soubor *. editorconfig* do kořenového adresáře projektu.

> [!TIP]
> Do projektu můžete přidat soubor. editorconfig tak, že kliknete pravým tlačítkem na projekt v **Průzkumník řešení** a vyberete **Přidat** > **novou položku**. V okně **Přidat novou položku** do vyhledávacího pole zadejte **editorconfig** . Vyberte šablonu **soubor editorconfig (výchozí)** a zvolte **Přidat**.
>
> ![Přidání položky editorconfig do projektu v aplikaci Visual Studio](media/add-editorconfig-file.png)

V současné době není k dispozici žádná hierarchická podpora pro kombinování souborů. editorconfig, které existují na různých úrovních adresáře, například řešení a na úrovni projektu.

### <a name="shared-configuration"></a>Sdílená konfigurace

Můžete sdílet soubor. editorconfig pro konfiguraci FxCop Analyzer mezi dvěma nebo více projekty, ale vyžaduje některé další kroky.

1. Uložte soubor *. editorconfig* do společného umístění.

2. Vytvořte soubor *. props* s následujícím obsahem:

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

3. Přidejte řádek do souboru *. csproj* nebo *. vbproj* pro import souboru *. props* , který jste vytvořili v předchozím kroku. Tento řádek musí být umístěn před řádky, které importují soubory FxCop Analyzer *. props* . Například pokud má soubor. props název *editorconfig. props*:

   ```xml
   ...
   <Import Project="..\..\editorconfig.props" Condition="Exists('..\..\editorconfig.props')" />
   <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
   ...
   ```

4. Znovu načtěte projekt.

> [!NOTE]
> Libovolné sdílené umístění souboru EditorConfig popsaného tady se týká jenom konfigurací analyzátorů FxCop. Pro další nastavení, jako je například odsazení a styl kódu, musí být soubor EditorConfig vždy umístěn ve složce projektu nebo v nadřazené složce.

## <a name="option-scopes"></a>Obory možností

Každou možnost lze nakonfigurovat pro všechna pravidla, pro kategorii pravidel (například pro pojmenování nebo návrh) nebo pro konkrétní pravidlo.

### <a name="all-rules"></a>Všechna pravidla

Syntaxe pro konfiguraci možnosti pro všechna pravidla je následující:

|Syntaxe|Příklad|
|-|-|
| dotnet_code_quality.OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>Kategorie pravidel

Syntaxe pro konfiguraci možnosti pro *kategorii* pravidel (například pojmenování, návrh nebo výkon) je následující:

|Syntaxe|Příklad|
|-|-|
| dotnet_code_quality.RuleCategory.OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>Konkrétní pravidlo

Syntaxe pro konfiguraci možnosti pro konkrétní pravidlo je následující:

|Syntaxe|Příklad|
|-|-|
| dotnet_code_quality.RuleId.OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="see-also"></a>Viz také:

- [Konfigurace analyzátoru](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [Analyzátory FxCop](install-fxcop-analyzers.md)
- [Konvence kódování .NET pro EditorConfig](../ide/editorconfig-code-style-settings-reference.md)
