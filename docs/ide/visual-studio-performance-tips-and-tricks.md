---
title: Rady a tipy pro zvýšení výkonu Visual Studio
ms.date: 08/31/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 2fbcb59e-e981-4b40-8b7a-c1140d31ec4b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08b2e1087b97cb16a52a8abdf8f204fd0f3a0bfb
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845194"
---
# <a name="visual-studio-performance-tips-and-tricks"></a>Rady a tipy pro zvýšení výkonu Visual Studio

Visual Studio výkonu doporučení jsou určené pro situace, nedostatek paměti, které může dojít ve výjimečných případech. V těchto situacích můžete optimalizovat určité funkce sady Visual Studio, které nemusí používat. Následující tipy nejsou určeny jako obecná doporučení.

> [!NOTE]
> Pokud máte potíže s používáním produktu z důvodu problémů s pamětí, dejte nám vědět prostřednictvím [zpětnou vazbu nástroj](../ide/how-to-report-a-problem-with-visual-studio-2017.md).

## <a name="use-a-64-bit-os"></a>Použít 64bitová verze OS

Pokud upgradujete systém z 32bitové verze systému Windows na 64bitovou verzi, rozbalte velikost virtuální paměti, které jsou k dispozici pro Visual Studio z 2 GB do 4 GB. To umožňuje sadě Visual Studio pro zpracování podstatně větší zatížení, i když je 32bitový proces.

Další informace najdete v tématu [paměťová omezení](https://msdn.microsoft.com/library/windows/desktop/aa366778(v=vs.85).aspx#memory_limits) a [použít/LARGEADDRESSAWARE v 64bitovém systému Windows](https://blogs.msdn.microsoft.com/oldnewthing/20050601-24/?p=35483/).

## <a name="disable-automatic-file-restore"></a>Zakázat automatické souboru obnovení

Visual Studio automaticky neotevře dokumenty, které byly ponechány otevřené v předchozí relace. To může prodloužit dobu potřebnou k načtení řešení až 30 % a víc, v závislosti na typu projektu a dokumenty otevíráte. Návrháři jako Windows Forms a XAML a některé JavaScript a typescript soubory, může být pomalé otevřete.

Visual Studio vás upozorní žlutě panelu při obnovení automatické dokumentů způsobuje řešení načíst výrazně pomalejší. Můžete zakázat automatické soubor znovu pomocí následujících kroků:

1. Vyberte **nástroje** > **možnosti** otevřete **možnosti** dialogové okno.

1. Na **projekty a řešení** > **Obecné** stránky, zrušte výběr **znovu otevřít dokumenty na zatížení řešení**.

Pokud zakážete automatické souboru obnovení, je rychlý způsob, jak přejděte na soubory, které chcete otevřít pomocí [přejít na](../ide/go-to.md). Vyberte **upravit** > **přejít na** > **přejděte na všechny**, nebo stiskněte klávesu **Ctrl**+**T** .

## <a name="configure-debugging-options"></a>Konfigurace možností ladění

Pokud jste se obvykle dostatek paměti během relace ladění, můžete optimalizovat výkon tím, že jeden nebo více změn konfigurace.

- **Povolit pouze můj kód**

    Nejjednodušší optimalizace je umožnit **pouze můj kód** funkci, která načte pouze symboly pro váš projekt. Povolení této funkce může způsobit velké paměti ukládání pro ladění spravované aplikace (.NET). Tato možnost je již povolená ve výchozím nastavení v některé typy projektů.

    Chcete-li povolit **pouze můj kód**, zvolte **nástroje** > **možnosti** > **ladění**  >   **Obecné**a potom vyberte **povolit volbu pouze vlastní kód**.

- **Zadejte symboly načíst**

    Pro nativní ladění načítání soubory symbolů (*PDB*) je nákladné z hlediska paměťových prostředků. Můžete nakonfigurovat nastavení ladicího programu symbol pro konzervaci paměti. Obvykle nakonfigurujte řešení jenom načíst moduly ze svého projektu.

    Chcete-li zadat symbol načítání, zvolte **nástroje** > **možnosti** > **ladění** > **symboly**.

    Nastavit na **pouze zadané moduly** místo **všechny moduly** a pak zadejte které moduly, které jsou pro vás k načtení. Při ladění, můžete můžete také kliknout pravým tlačítkem v určitých modulech **moduly** okno explicitně zahrnout modul zatížení symbol. (Chcete-li otevřít okno při ladění, zvolte **ladění** > **Windows** > **moduly**.)

    Další informace najdete v tématu [pochopit soubory symbolů](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/).

- **Zakázat diagnostické nástroje**

    Doporučuje se zakázat procesoru profilace po použití. Tato funkce může využívat velké množství prostředků. Po povolení procesoru profilace tento stav je zachová pro následné ladicí relace, proto je vhodné explicitně vypnutí, pokud provádí. Některé prostředky, může uložit zakázáním diagnostické nástroje při ladění, pokud nepotřebujete funkce zadaná.

    Zakázání **diagnostické nástroje**, spustit relaci ladění, zvolte **nástroje** > **možnosti** > **povolení diagnostiky Nástroje pro**a zrušte výběr možnosti.

    Další informace najdete v tématu [nástrojích pro profilaci](../profiling/profiling-tools.md).

## <a name="disable-tools-and-extensions"></a>Zakázat nástroje a rozšíření

Některé nástroje nebo rozšíření může být vypnuto ke zlepšení výkonu.

> [!TIP]
> Často můžete izolovat problémy s výkonem vypnutím rozšíření jeden najednou a opětná kontrola výkonu.

### <a name="managed-language-service-roslyn"></a>Spravovaná služba jazyka (Roslyn)

Informace o aspektech týkajících se výkonu kompilátoru platformu .NET ("Roslyn") najdete v tématu [důležité informace o výkonu pro velká řešení](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).

- **Zakázat úplnou analýzu řešení**

    Visual Studio provádí analýzu na celé řešení Chcete-li poskytovat bohaté prostředí o chybách před vyvoláním sestavení. Tato funkce je užitečná k identifikaci chyby co nejdříve. Pro velká řešení, ale tato funkce může využít významné paměťových prostředků. Pokud dojde k přetížení paměti nebo podobné problémy, můžete zakázat toto prostředí pro uvolnění těchto prostředků. Ve výchozím nastavení tato možnost je povolena v jazyce Visual Basic a zakázané pro jazyk C#.

    Zakázat **analýzy celého řešení**, zvolte **nástroje** > **možnosti** > **textového editoru**, zvolte položku buď **jazyka Visual Basic** nebo **C#**. Zvolte **Upřesnit** a zrušte výběr **povolit úplnou analýzu řešení**.

- **Zakázat Codelensu**

    Visual Studio provádí **najít všechny odkazy** úloh na každou metodu, jak je uvedeno. Codelensu poskytuje funkce, jako je například zobrazení vložený počet odkazů. Práce se provádí v samostatném procesu, jako *ServiceHub.RoslynCodeAnalysisService32*. U velkých řešení, nebo na systémech omezené prostředků tato funkce může mít významný dopad na výkon. Pokud dojde k problémům s pamětí, například při načítání velkých řešení na počítač 4 GB nebo vysoké využití procesoru pro tento proces můžete zakázat Codelensu tím se uvolní prostředky.

    Chcete-li zakázat **Codelensu**, zvolte **nástroje** > **možnosti** > **textového editoru**  >   **Všechny jazyky** > **Codelensu**a zrušte výběr funkce.

    > [!NOTE]
    > Codelensu je k dispozici v edicích sady Visual Studio Professional a Enterprise.

### <a name="other-tools-and-extensions"></a>Další nástroje a rozšíření

- **Zakázání rozšíření**

    Rozšíření jsou další softwarové součásti přidat do sady Visual Studio, které přinášejí nové funkce nebo rozšířit stávající funkce. Rozšíření může být často zdroj problémy prostředků paměti. Pokud dojde k potížím s prostředky paměti, zkuste zakázat rozšíření jeden současně zobrazíte jak ovlivňuje pro scénáře nebo pracovní postup.

    Pokud chcete zakázat rozšíření, přejděte na **nástroje** > **rozšíření a aktualizace**a konkrétní rozšíření zakázat.

- **Zakázat Návrhář XAML**

    Návrhář XAML je ve výchozím nastavení povolené, ale pouze spotřebovává prostředky, pokud můžete otevřít *XAML* souboru. Pokud pracovat se soubory XAML, ale nechcete, aby používat návrháře funkce, zakažte tuto funkci, uvolněte část paměti.

    Chcete-li zakázat **návrháře XAML**, přejděte na **nástroje** > **možnosti** > **návrháře XAML**  >  **Povolit návrháře XAML**a zrušte výběr možnosti.

- **Odebrat úlohy**

    Instalační program Visual Studio můžete použít k odebrání úlohy, které se již nepoužívají. Tato akce může zjednodušit náklady na spuštění a runtime přeskočením balíčky a sestavení, které již nejsou potřebné.

## <a name="force-a-garbage-collection"></a>Vynutit kolekce paměti

Modul CLR používá systém uvolňování paměti kolekce paměti správy. V tomto systému někdy paměti používá objekty, které už nejsou potřeba. Tento stav je dočasný; uvolňování paměti vydá tuto paměť na základě jejího výkonu a heuristiky využití prostředků. Můžete vynutit CLR ke shromažďování všech nevyužitou paměť pomocí klávesové zkratky v sadě Visual Studio. Pokud je významné množství paměti čekání kolekce a můžete vynutit uvolnění paměti, měli byste vidět využití paměti *devenv.exe* proces vyřadit **Správce úloh**. Je občas nutné k použití této metody. Ale po dokončení náročná operace (například úplné sestavení, relaci ladění nebo řešení otevřete událost) může pomoct určit, kolik paměti je opravdu používá proces. Protože Visual Studio je přimíchán, spravované & (nativní), je někdy možné nativní přidělování a uvolňování pokouší o omezené paměťových prostředků. V podmínkách velké množství paměti může pomoct vynutit uvolňování paměti spusťte.

Chcete-li vynutit uvolnění paměti, použijte klávesová zkratka: **Ctrl**+**Alt**+**Shift**+**F12**, **Ctrl**+**Alt**+**Shift**+**F12** (ho dvakrát stiskněte).

Pokud vynucení uvolňování paměti spolehlivě provede váš scénář fungovat, soubor sestavy pomocí nástroje Visual Studio zpětnou vazbu, jak toto chování je pravděpodobné, že chyby.

Podrobný popis garbage collector v CLR, najdete v části [základy uvolnění paměti](/dotnet/standard/garbage-collection/fundamentals).

## <a name="see-also"></a>Viz také:

- [Optimalizace výkonu v sadě Visual Studio](../ide/optimize-visual-studio-performance.md)
- [Spouštění řešení rychlejší (blog Visual Studio)](https://blogs.msdn.microsoft.com/visualstudio/2018/04/04/load-solutions-faster-with-visual-studio-2017-version-15-6/)