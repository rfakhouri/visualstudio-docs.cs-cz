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
ms.openlocfilehash: cae7a02c774773d08c287dde7df59ff62fdbec58
ms.sourcegitcommit: 9cfd3ef6c65f671a26322320818212a1ed5955fe
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/26/2019
ms.locfileid: "68533339"
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>Přehled analyzátorů .NET Compiler Platform

Analyzátory .NET Compiler Platform ("Roslyn") analyzují kód pro styl, kvalitu a udržovatelnost, návrh a další problémy. Sada Visual Studio obsahuje integrovanou sadu analyzátorů, které analyzují C# nebo Visual Basic kód při psaní. Předvolby pro tyto integrované analyzátory můžete nakonfigurovat na stránce [Možnosti textový editor](../ide/code-styles-and-code-cleanup.md) nebo v [souboru. editorconfig](../ide/editorconfig-code-style-settings-reference.md). Další analyzátory můžete nainstalovat jako rozšíření sady Visual Studio nebo balíček NuGet.

Pokud je porušení pravidel Nalezeno analyzátorem, jsou hlášeny v editoru kódu (jako vlnovku pod problematickým  kódem) a v okně **Seznam chyb** .

Mnoho pravidel analyzátoru nebo *diagnostiky*má jednu nebo více souvisejících *oprav kódu* , které můžete použít pro opravu problému. Diagnostika analyzátoru, která je součástí sady Visual Studio, má přidruženou opravu kódu. Opravy kódu se zobrazují v nabídce ikony žárovky spolu s dalšími typy rychlých [akcí](../ide/quick-actions.md). Informace o těchto opravách kódu najdete v tématu [běžné rychlé akce](../ide/common-quick-actions.md).

![Porušení analyzátoru a oprava kódu rychlé akce](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>Analyzátory Roslyn vs. Statická analýza kódu

Analyzátory .NET Compiler Platform ("Roslyn") nakonec nahradí [statickou analýzu kódu](../code-quality/code-analysis-for-managed-code-overview.md) pro spravovaný kód. Mnoho pravidel analýzy statických kódu již bylo přepsáno jako Diagnostika analyzátoru Roslyn.

Podobně jako porušení pravidel statického pravidla analýzy kódu se v **Seznam chyb**zobrazí porušení analyzátoru Roslyn. Kromě toho se v editoru kódu zobrazí také narušení Roslyn analyzátoru, jako *vlnovky* pod problematickým kódem. Barva vlnovky závisí na [nastavení závažnosti](../code-quality/use-roslyn-analyzers.md#rule-severity) pravidla. Následující snímek obrazovky ukazuje tři porušení&mdash;jedna červená, jedna zelená a jedna šedá:

![Vlnovky v editoru kódu](media/diagnostics-severity-colors.png)

Analyzátory Roslyn analyzují kód v době sestavování, jako je třeba Analýza statického kódu, pokud je povolená, ale také při psaní živě. Pokud povolíte [úplnou analýzu řešení](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis), analyzátory Roslyn také poskytují analýzu kódu v době návrhu, které nejsou otevřeny v editoru.

> [!TIP]
> Chyby při sestavování a varování z analyzátorů Roslyn jsou zobrazeny pouze v případě, že analyzátory jsou nainstalovány jako balíček NuGet.

Pouze analyzátory Roslyn pouze sestavují stejné typy problémů, které provádí analýza statického kódu, ale usnadňují odstranění jednoho nebo všech výskytů porušení v souboru nebo projektu. Tyto akce se nazývají *opravy kódu*. Opravy kódu jsou specifické pro IDE; v aplikaci Visual Studio jsou implementovány jako [rychlé akce](../ide/quick-actions.md). Ne všechny diagnostické nástroje analyzátoru mají přidruženou opravu kódu.

> [!NOTE]
> Následující možnosti uživatelského rozhraní se vztahují pouze na statickou analýzu kódu:
>
> - Možnost nabídky analýza**kódu spuštění**  > 
> - Zaškrtnutí políčka **Povolit analýzu kódu při sestavení** a potlačení **výsledků z vygenerovaného kódu** se zobrazí na kartě **Analýza kódu** stránky vlastností projektu (tyto možnosti nejsou nijak ovlivněny analyzátory Roslyn).

Chcete-li rozlišovat mezi porušením analyzátorů Roslyn a analýzou statického kódu v **Seznam chyb**, podívejte se do sloupce **nástroje** . Pokud hodnota nástroje odpovídá jednomu ze sestavení analyzátoru v **Průzkumník řešení**, například **Microsoft. CodeQuality. analyzers**, narušení pochází z analyzátoru Roslyn. V opačném případě porušení vychází ze statické analýzy kódu.

![Sloupec nástroje v Seznam chyb](media/code-analysis-tool-in-error-list.png)

> [!TIP]
> Vlastnost **RunCodeAnalysis** MSBuild v souboru projektu se vztahuje pouze na statickou analýzu kódu. Pokud nainstalujete analyzátory, nastavte **RunCodeAnalysis** na **hodnotu false** v souboru projektu, abyste zabránili spuštění analýzy statického kódu po sestavení.
>
> ```xml
> <RunCodeAnalysis>false</RunCodeAnalysis>
> ```

## <a name="nuget-package-versus-vsix-extension"></a>Balíček NuGet versus rozšíření VSIX

Analyzátory .NET Compiler Platform lze instalovat podle projektu prostřednictvím balíčku NuGet nebo sady Visual Studio – v rámci rozšíření sady Visual Studio. Existují některé rozdíly v chování při [instalaci analyzátorů](../code-quality/install-roslyn-analyzers.md)mezi těmito dvěma způsoby.

### <a name="scope"></a>Scope

Pokud nainstalujete analyzátory jako rozšíření sady Visual Studio, vztahují se na úroveň řešení na všechny instance sady Visual Studio. Pokud nainstalujete analyzátory jako balíček NuGet, což je upřednostňovaná metoda, vztahují se pouze na projekt, ve kterém byl balíček NuGet nainstalován. V týmových prostředích jsou analyzátory nainstalované jako balíčky NuGet v oboru pro *všechny vývojáře* , kteří na daném projektu pracují.

### <a name="build-errors"></a>Chyby sestavení

Pokud chcete, aby byla pravidla vynutila při sestavování, včetně prostřednictvím příkazového řádku nebo v rámci sestavení kontinuální integrace (CI), nainstalujte analyzátory jako balíček NuGet. V sestavě sestavení se nezobrazují upozornění a chyby analyzátoru, pokud nainstalujete analyzátory jako rozšíření.

Následující snímek obrazovky ukazuje výstup sestavení z příkazového řádku z sestavení projektu, který obsahuje narušení pravidla analyzátoru:

![Výstup nástroje MSBuild s porušením pravidla](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>Závažnost pravidla

Nemůžete nastavit závažnost pravidel z analyzátorů, které se nainstalovaly jako rozšíření sady Visual Studio. Pokud chcete nakonfigurovat [závažnost pravidla](../code-quality/use-roslyn-analyzers.md#rule-severity), nainstalujte analyzátory jako balíček NuGet.

## <a name="categories"></a>Kategorie

Níže jsou uvedeny různé typy analyzátorů, které vám pomohou analyzovat váš kód:

- Doporučené analyzátory Microsoftu: [Analyzátory FxCop](../code-quality/fxcop-analyzers.yml)
- Analyzátory rozhraní IDE sady Visual Studio: [EditorConfig](../ide/code-styles-and-code-cleanup.md)
- Analyzátory třetích stran: [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator/), [analyzátory XUnit](https://www.nuget.org/packages/xunit.analyzers/), [analyzátor sonar](https://www.nuget.org/packages/SonarAnalyzer.CSharp/)

## <a name="next-steps"></a>Další postup

> [!div class="nextstepaction"]
> [Instalace analyzátorů Roslyn v aplikaci Visual Studio](../code-quality/install-roslyn-analyzers.md)

> [!div class="nextstepaction"]
> [Použití analyzátorů Roslyn v aplikaci Visual Studio](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Viz také:

- [Nejčastější dotazy k analyzátorům](analyzers-faq.md)
- [Psaní vlastního analyzátoru Roslyn](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET Compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)
