---
title: Analýza kódu pomocí analyzátorů Roslyn
ms.date: 03/26/2018
ms.topic: overview
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ba1529840a38a23929b9926cc4bed5cc22a058cb
ms.sourcegitcommit: 36f5ffd6ae3215fe31837f4366158bf0d871f7a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/08/2019
ms.locfileid: "59232564"
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>Přehled analyzátory pro .NET Compiler Platform

.NET compiler Platform ("Roslyn") analyzátory analyzovat svůj kód pro styl, kvality a udržovatelnosti, návrhu a další potíže. Visual Studio obsahuje integrované sady analyzátory, které analyzují vaše C# nebo kódu jazyka Visual Basic jako vy, zadejte. Konfigurace předvoleb pro tyto integrované analyzátorů na [textový editor možnosti](../ide/code-styles-and-quick-actions.md) stránky nebo [souboru .editorconfig](../ide/editorconfig-code-style-settings-reference.md). Jako rozšíření sady Visual Studio nebo pomocí balíčku NuGet můžete nainstalovat další analyzátory.

Pokud analyzátor se objevila porušení pravidel, jsou hlášeny v editoru kódu (jako *podtržení* pod problematický kód) a **seznam chyb** okno.

Mnoho pravidla analyzátoru nebo *diagnostiky*, mají jednu nebo více přidružené *opravy kódu* , můžete použít k opravě problému. Diagnostika analyzátoru, které jsou součástí sady Visual Studio máte to napravit přidružený kód. Opravy kódu se zobrazují v nabídce ikonu žárovky společně s další typy [rychlé akce](../ide/quick-actions.md). Informace o těchto opravy kódu, naleznete v tématu [běžné rychlé akce](../ide/common-quick-actions.md).

![Analýza porušení a opravu kódu rychlé akce](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>Analyzátory Roslyn a statické analýzy kódu

Analyzátory .NET compiler Platform ("Roslyn") bude nakonec nahradí [statickou analýzu kódu](../code-quality/code-analysis-for-managed-code-overview.md) pro spravovaný kód. Mnoho pravidel analýzy kódu statických již byla přepsali jsme jako Roslyn analyzátor diagnostiky.

Jako je porušení pravidel pro analýzu statického kódu, porušení analyzátor Roslyn joinkind **seznam chyb**. Kromě toho Roslyn analyzátor porušení zobrazí také v editoru kódu jako *squigglies* pod problematický kód. Barva podtržení závisí [nastavení závažnosti](../code-quality/use-roslyn-analyzers.md#rule-severity) pravidla. Následující snímek obrazovky ukazuje tři porušení&mdash;jeden červené, jedna, zelené a jeden gray:

![Squigglies v editoru kódu](media/diagnostics-severity-colors.png)

Analyzátory Roslyn analýza kódu v okamžiku sestavení, jako je analýza statického kódu, pokud je povoleno, ale také na live při psaní. Pokud povolíte [úplné analýzy řešení](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis), analyzátorů Roslyn také poskytují analýzu návrhu soubory kódu, které nejsou otevřené v editoru.

> [!TIP]
> Čas sestavení chyby a upozornění z analyzátory Roslyn se zobrazí, jenom Pokud jsou nainstalované analyzátory jako balíček NuGet.

Pouze proveďte analyzátory Roslyn sestavy stejné typy problémů, které provádí statickou analýzu kódu, ale jejich usnadňují vás nutí opravovat jednu nebo všechny výskyty narušení v souboru nebo projektu. Tyto akce jsou volány *opravy kódu*. Opravy kódu jsou specifické pro prostředí IDE; v sadě Visual Studio, jsou implementovány jako [rychlé akce](../ide/quick-actions.md). Ne všechny analyzátor diagnostiky mít to napravit přidružený kód.

> [!NOTE]
> Tyto možnosti uživatelského rozhraní platí pouze pro statickou analýzu kódu:
>
> - **Analyzovat** > **spustit analýzu kódu** nabídky.
> - **Povolit analýzu kódu na sestavení** a **potlačit Výsledky generovaného kódu** zaškrtávacích políček na **analýzy kódu** kartu (tyto možnosti nemají stránky vlastností projektu vliv na analyzátory Roslyn).

Rozlišovat mezi porušení z analyzátory Roslyn a statickou analýzu kódu v **seznam chyb**, podívejte se na **nástroj** sloupce. Pokud nástroj hodnota odpovídá jednomu z sestavení analyzátoru v **Průzkumníka řešení**, například **Microsoft.CodeQuality.Analyzers**, porušení pochází z Roslyn analyzátor. V opačném případě porušení pochází ze statické analýzy kódu.

![Nástroj pro sloupec v seznamu chyb](media/code-analysis-tool-in-error-list.png)

> [!TIP]
> **RunCodeAnalysis** vlastnost msbuild v souboru projektu se týká pouze statické analýzy kódu. Pokud nainstalujete analyzátory, nastavte **RunCodeAnalysis** k **false** v souboru projektu, aby se zabránilo statickou analýzu kódu po dokončení sestavení.
>
> ```xml
> <RunCodeAnalysis>false</RunCodeAnalysis>
> ```

## <a name="nuget-package-versus-vsix-extension"></a>Balíček NuGet a rozšíření VSIX

Sada .NET compiler Platform analyzátory může být nainstalována na projektu prostřednictvím balíčku NuGet, nebo Visual Studio na úrovni jako rozšíření sady Visual Studio. Existují některé klíčové rozdíly mezi těmito dvěma metodami [instalace analyzátorů](../code-quality/install-roslyn-analyzers.md).

### <a name="scope"></a>Rozsah

Pokud nainstalujete analyzátory jako rozšíření sady Visual Studio, na všechny instance sady Visual Studio se vztahují na úrovni řešení. Pokud nainstalujete analyzátory jako balíček NuGet, který je upřednostňovanou metodou, se vztahují pouze k projektu, kam se nainstaloval balíček NuGet. V prostředích team analyzátory nainstalována jako balíčky NuGet jsou v oboru pro *všichni vývojáři* , které fungují v daném projektu.

### <a name="build-errors"></a>Chyby sestavení

Pokud chcete mít nastavená pravidla vynucovat v okamžiku sestavení, včetně prostřednictvím příkazového řádku nebo v rámci kontinuální integrace (CI) sestavení, nainstalujte analyzátory jako balíček NuGet. Analyzátor upozornění a chyby nezobrazují v sestavě sestavení při instalaci analyzátory jako rozšíření.

Následující snímek obrazovky ukazuje sestavení z příkazového řádku výstup z operace sestavení projektu, který obsahuje porušení pravidla analyzátoru:

![Výstup nástroje MSBuild s porušení pravidla](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>Závažnost pravidla

Závažnost pravidla nelze nastavit v analyzátory, které byly nainstalovány jako rozšíření sady Visual Studio. Ke konfiguraci [pravidlo závažnost](../code-quality/use-roslyn-analyzers.md#rule-severity), instalace analyzátorů jako balíček NuGet.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Instalace analyzátorů Roslyn v sadě Visual Studio](../code-quality/install-roslyn-analyzers.md)

> [!div class="nextstepaction"]
> [Používání analyzátorů Roslyn v sadě Visual Studio](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Viz také:

- [Nejčastější dotazy k analyzátorům](analyzers-faq.md)
- [Napsat vlastní analyzátor Roslyn](../extensibility/getting-started-with-roslyn-analyzers.md)
- [Sada .NET Compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)