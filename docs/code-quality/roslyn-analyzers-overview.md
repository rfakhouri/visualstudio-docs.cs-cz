---
title: Roslyn analyzátorů v sadě Visual Studio | Microsoft Docs
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 35b052c795ae10b7d7c4f96c8c4fce72ecbee839
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>Přehled platformy .NET kompilátoru analyzátory

Visual Studio 2017 zahrnuje integrovanou sadu analyzátorů kompilátoru platformy .NET, které při psaní analýza kódu C# nebo Visual Basic. Jako balíčku NuGet, můžete nainstalovat další analyzátorů jako rozšíření sady Visual Studio, nebo na jednotlivých projektů. Podívejte se na kód styl, kvality kódu a udržovatelnosti, návrh kódu a další problémy analyzátorů.

Pokud jsou funkcí Analýza porušení pravidel, se zvyšují v editoru kódu jako *vlnovkou* pod kód problematické a v **seznam chyb**.

Mnoho pravidla analyzátoru nebo *diagnostiky*, mít jeden nebo více přidružené *code opravy* , můžete použít k odstranění problému. Analyzátor diagnostiky, které jsou součástí sady Visual Studio mít oprava přidružený kód. V nabídce ikonu žárovky společně s jiné typy jsou uvedeny opravy kódu *rychlé akce*. Informace o tyto opravy kódu najdete v tématu [běžné rychlé akce](../ide/common-quick-actions.md).

![Analyzátor porušení a opravte kód rychlé akce](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>Roslyn analyzátorů oproti Statická analýza kódu

Nakonec analyzátorů kompilátoru platformu .NET ("Roslyn") nahradí [analýza statické kódu](../code-quality/code-analysis-for-managed-code-overview.md) pro spravovaný kód. Řadu pravidel analýzy kódu statických mít již přepsána jako Roslyn analyzátor diagnostiky.

Jako je porušení pravidel analýzy kódu statických, porušení analyzátor Roslyn zobrazí v **seznam chyb**. Kromě toho Roslyn analyzátor porušení také zobrazí v editoru kódu jako *squigglies* pod problematické kódu. Barva vlnovkou závisí na [nastavení závažnosti](../code-quality/use-roslyn-analyzers.md#rule-severity) pravidla. Následující snímek obrazovky ukazuje tři porušení&mdash;jednomu red, jeden zelený a jeden gray:

![Squigglies v editoru kódu](media/diagnostics-severity-colors.png)

Roslyn analyzátorů analýza kódu v době sestavení, jako je analýza statické kódu, pokud je povoleno, ale také live při psaní! Roslyn analyzátorů můžete zadat taky návrhu analýzu soubory kódu, které nejsou otevřen v editoru, pokud povolíte [úplné analýzy řešení](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis).

> [!NOTE]
> Čase vytvoření buildu chyby a upozornění z Roslyn analyzátorů se zobrazí, jenom Pokud Analyzátory se instalují jako balíčku NuGet.

Pouze provést Roslyn analyzátorů sestavy stejné typy problémy, které nemá analýza statické kódu, ale jejich snadno můžete opravit jednoho nebo všech výskytů porušení v souboru nebo projektu. Tyto akce se nazývají *code opravy*. Opravy kódu jsou specifické pro IDE; v sadě Visual Studio jsou implementované jako [rychlé akce](../ide/quick-actions.md). Ne všechny diagnostiky analyzátor mít oprava přidružený kód.

> [!NOTE]
> Možnost nabídky **analyzovat** > **spuštění analýzy kódu** se vztahuje pouze na statickou analýzu kódu. Kromě toho na projektu **analýza kódu** stránka vlastností **povolit analýza kódu v sestavení** a **potlačit výsledky z generovaného kódu** zaškrtávací políčka platí pouze pro Analýza kódu statické. Nemají žádný vliv na Roslyn analyzátorů.

K rozlišení mezi porušení z Roslyn analyzátorů a analýza statické kódu v **seznam chyb**, podívejte se na **nástroj** sloupce. Pokud nástroj hodnota odpovídá jednomu z analyzátor sestavení v **Průzkumníku řešení**, například **Microsoft.CodeQuality.Analyzers**, porušení pochází z Roslyn analyzátor. Narušení, jinak hodnota pochází z analýza statické kódu.

![Nástroj pro sloupec v seznamu chyb](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-vs-extension"></a>Balíček NuGet oproti rozšíření

Kompilátoru platformu .NET, který může být analyzátorů nainstalovat na projektu prostřednictvím balíčku NuGet, nebo Visual Studio celou jako rozšíření sady Visual Studio. Existují určité rozdíly klíče chování mezi tyto dvě metody [instalaci analyzátorů](../code-quality/install-roslyn-analyzers.md).

### <a name="scope"></a>Rozsah

Pokud instalujete analyzátorů jako rozšíření sady Visual Studio, vztahují se na úrovni řešení pro všechny instance sady Visual Studio. Pokud instalujete analyzátory jako balíčku NuGet, který je upřednostňovaná metoda, se vztahují pouze k projektu, které byl nainstalován balíček NuGet. V prostředích team analyzátorů nainstalovat jako balíčky NuGet jsou v oboru pro *všechny vývojáře* že fungovat na tomto projektu.

### <a name="build-errors"></a>Chyby sestavení

Tak, aby měl pravidla vynucují v čase vytvoření buildu, včetně pomocí příkazového řádku nebo jako součást průběžnou integraci sestavení (CI), nainstalujte analyzátory jako balíčku NuGet. Analyzátor upozornění a chyby nejsou zobrazena v sestavě sestavení při instalaci analyzátory jako rozšíření.

Následující snímek obrazovky ukazuje vytváření projekt, který obsahuje pravidlo porušení analyzátor výstup sestavení příkazového řádku:

![Výstup nástroje MSBuild s porušení pravidel](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>Pravidlo závažnosti

Nelze nastavit závažnost pravidla z analyzátory, které byly nainstalovány jako rozšíření sady Visual Studio. Ke konfiguraci [pravidlo závažnost](../code-quality/use-roslyn-analyzers.md#rule-severity), nainstalujte analyzátory jako balíčku NuGet.

## <a name="next-steps"></a>Další kroky

- [Nainstalujte Roslyn analyzátorů v sadě Visual Studio](../code-quality/install-roslyn-analyzers.md)
- [Použití Roslyn analyzátorů v sadě Visual Studio](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Viz také

- [Rychlé akce v sadě Visual Studio](../ide/quick-actions.md)
- [Zápis vlastní analyzátor Roslyn](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET Compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)