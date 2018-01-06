---
title: "Rady a tipy pro zvýšení výkonu sady Visual Studio | Microsoft Docs"
ms.date: 08/31/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: 2fbcb59e-e981-4b40-8b7a-c1140d31ec4b
caps.latest.revision: "1"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b703fd45732e3fd083a5c95b68647f67dce57b3a
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="visual-studio-performance-tips-and-tricks"></a>Rady a tipy pro zvýšení výkonu sady Visual Studio

Visual Studio výkonu doporučení jsou určené pro situace, nedostatek paměti, které může dojít ve výjimečných případech. V těchto situacích můžete optimalizovat určité funkce sady Visual Studio, které nemusí používat. Následující tipy nejsou určeny jako obecná doporučení.

> [!NOTE]
> Pokud máte potíže s používáním produktu z důvodu problémů s pamětí, dejte nám vědět prostřednictvím nástroje zpětnou vazbu.

## <a name="optimize-your-environment"></a>Optimalizace prostředí

- **Použít 64bitová verze operačního systému**

    Pokud upgradujete systém z 32bitové verze systému Windows na 64bitovou verzi, rozbalte velikost virtuální paměti, které jsou k dispozici pro Visual Studio z 2 GB do 4 GB. To umožňuje sadě Visual Studio pro zpracování podstatně větší zatížení, i když je 32bitový proces.

    Další informace najdete v tématu [paměťová omezení](https://msdn.microsoft.com/en-us/library/windows/desktop/aa366778(v=vs.85).aspx#memory_limits) a [pomocí/LARGEADDRESSAWARE na 64bitovém systému Windows](https://blogs.msdn.microsoft.com/oldnewthing/20050601-24/?p=35483/).

## <a name="configure-solution-and-projects"></a>Konfigurace řešení a projekty

Pokud máte velké řešení s mnoha projektů, může mít užitek tím, že provedete následující optimalizace:

- **Uvolnění projekty**

    Můžete ručně uvolnit zřídka používané jednotlivých projektů v Průzkumníku řešení pomocí místní nabídky klikněte pravým tlačítkem.

- **Refaktorovat řešení**

    Řešení můžete rozdělit na několik menších souborů řešení s běžně používanými projekty. Tato refaktoring by výrazně snížit využití paměti pro pracovní postup. Menší řešení načíst také rychlejší.

## <a name="configure-debugging-options"></a>Konfigurace možností ladění
Pokud jste se obvykle dostatek paměti během relace ladění, můžete optimalizovat výkon tím, že jeden nebo více změn konfigurace.

- **Povolit pouze můj kód**

    Nejjednodušší optimalizace je umožnit **pouze můj kód** funkci, která načte pouze symboly pro váš projekt. Povolení této funkce může způsobit velké paměti ukládání pro ladění spravované aplikace (.NET). Tato možnost je již povolená ve výchozím nastavení v některé typy projektů.

    Chcete-li povolit **pouze můj kód**, zvolte **nástroje > Možnosti > ladění > Obecné**a potom vyberte **povolit volbu pouze vlastní kód**.

- **Zadejte symboly načíst**

    Pro nativní ladění načítání souborů symbolu (.pdb) je nákladné z hlediska paměťových prostředků. Můžete nakonfigurovat nastavení ladicího programu symbol pro konzervaci paměti. Obvykle nakonfigurujte řešení jenom načíst moduly ze svého projektu.

    Chcete-li zadat symbol načítání, zvolte **nástroje > Možnosti > ladění > symboly**.

    Nastavit na **pouze zadané moduly** místo **všechny moduly** a pak zadejte které moduly, které jsou pro vás k načtení. Při ladění, můžete můžete také kliknout pravým tlačítkem v určitých modulech **moduly** okno explicitně zahrnout modul zatížení symbol. (Chcete-li otevřít okno při ladění, zvolte **ladění > Windows > moduly**.)

    Další informace najdete v tématu [pochopení soubory symbolů](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/).

- **Zakázat diagnostické nástroje**

    Doporučuje se zakázat procesoru profilace po použití. Tato funkce může využívat velké množství prostředků. Po povolení procesoru profilace tento stav je zachová pro následné ladicí relace, proto je vhodné explicitně vypnutí, pokud provádí. Některé prostředky, může uložit zakázáním diagnostické nástroje při ladění, pokud nepotřebujete funkce zadaná.

    Chcete-li zakázat diagnostické nástroje, spustit relaci ladění, zvolte **nástroje > Možnosti > Povolit diagnostické nástroje**a zrušte výběr možnosti.

    Další informace najdete v tématu [nástrojích pro profilaci](../profiling/profiling-tools.md).

## <a name="disable-tools-and-extensions"></a>Zakázat nástroje a rozšíření
Některé nástroje nebo rozšíření může vypnuté ke zlepšení výkonu.

> [!TIP]
> Často můžete izolovat problémy s výkonem vypnutím rozšíření jeden najednou a opětná kontrola výkonu.

### <a name="managed-language-services-roslyn"></a>Jazyk spravované služby (Roslyn)

Informace o aspektech týkajících se výkonu Roslyn najdete v tématu [důležité informace o výkonu pro velká řešení] (https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).

- **Zakázat úplnou analýzu řešení**

    Visual Studio provádí analýzu na celé řešení Chcete-li poskytovat bohaté prostředí o chybách před vyvoláním sestavení. Tato funkce je užitečná k identifikaci chyby co nejdříve. Pro velmi velká řešení, ale tato funkce spotřebovat významné paměťových prostředků. Pokud dojde k přetížení paměti nebo podobné problémy, můžete zakázat toto prostředí pro uvolnění těchto prostředků. Ve výchozím nastavení tato možnost je povolena v jazyce Visual Basic a zakázané pro jazyk C#.

    Chcete-li zakázat **analýzy celého řešení**, zvolte **nástroje > Možnosti > textový Editor >< Visual Basic a C# >**. Zvolte **Upřesnit** a zrušte výběr **povolit úplnou analýzu řešení**.

- **Zakázat Codelensu**

    Visual Studio provádí **najít všechny odkazy** úloh na každou metodu, jak je uvedeno. Codelensu poskytuje funkce, jako je například zobrazení vložený počet odkazů. Práce se provádí v samostatném procesu (například ServiceHub.RoslynCodeAnalysisService32). Ve velmi velkých řešeních nebo na systémech prostředků omezené tato funkce může mít významný dopad na výkon, i když se spustí s nízkou prioritou. Pokud dojde k vysoké využití procesoru v tomto procesu nebo paměti problémy (například při načítání velkých řešení na počítači, 4 GB), můžete zkusit zakázáním této funkce tím se uvolní prostředky.

    Chcete-li zakázat Codelensu, zvolte **nástroje > Možnosti > textový Editor > všechny jazyky > Codelensu**a zrušit zaškrtnutí políčka funkci.

    Tato funkce je k dispozici v aplikaci Visual Studio Professional a Visual Studio Enterprise.

### <a name="other-tools-and-extensions"></a>Další nástroje a rozšíření

- **Zakázání rozšíření**

    Rozšíření jsou další softwarové součásti přidat do sady Visual Studio, které přinášejí nové funkce nebo rozšířit stávající funkce. Rozšíření může být často zdroj problémy prostředků paměti. Pokud dojde k potížím s prostředky paměti, zkuste zakázat rozšíření jeden současně zobrazíte jak ovlivňuje pro scénáře nebo pracovní postup.

    Pokud chcete zakázat rozšíření, přejděte na **nástroje | Rozšíření a aktualizace**a konkrétní rozšíření zakázat.

- **Zakázat Návrhář XAML**

    Návrhář XAML je ve výchozím nastavení povolené, ale pouze spotřebovává prostředky, pokud můžete otevřít. Souboru XAML. Pokud pracovat se soubory XAML, ale nechcete, aby používat návrháře funkce, zakažte tuto funkci, uvolněte část paměti.

    Chcete-li zakázat návrháře XAML, přejděte na **nástroje > Možnosti > návrháře XAML > Povolit Návrhář XAML**a zrušte výběr možnosti.

- **Odebrat úlohy**

    Instalační program Visual Studio můžete použít k odebrání úlohy, které se již nepoužívají. Tato akce může zjednodušit náklady na spuštění a runtime přeskočením balíčky a sestavení, které již nejsou potřebné.

## <a name="force-a-garbage-collection"></a>Vynutit kolekce paměti

Modul CLR používá systém uvolňování paměti kolekce paměti správy. V tomto systému někdy paměti používá objekty, které už nejsou potřeba. Tento stav je dočasný; uvolňování paměti vydá tuto paměť na základě jejího výkonu a heuristiky využití prostředků. Můžete vynutit CLR ke shromažďování všech nevyužitou paměť pomocí klávesové zkratky v sadě Visual Studio. Pokud je významné množství paměti čekání kolekce a můžete vynutit uvolnění paměti, měli byste vidět využití paměti procesu devenv.exe vyřadit ve Správci úloh. Je občas nutné k použití této metody. Ale po dokončení náročná operace (například úplné sestavení, relaci ladění nebo řešení otevřete událost) může pomoct určit, kolik paměti je opravdu používá proces. Protože Visual Studio je přimíchán, spravované & (nativní), je někdy možné nativní přidělování a uvolňování pokouší o omezené paměťových prostředků. V podmínkách velké množství paměti může pomoct vynutit uvolňování paměti spusťte.

Chcete-li vynutit uvolnění paměti, použijte klávesová zkratka: **Ctrl + Alt + Shift + F12**, **Ctrl + Alt + Shift + F12** (ho dvakrát stiskněte).

Pokud vynucení uvolňování paměti spolehlivě provede váš scénář fungovat, soubor sestavy pomocí nástroje Visual Studio zpětnou vazbu, jak toto chování je pravděpodobné, že chyby.

Podrobný popis garbage collector v CLR, najdete v části [základní z kolekce paměti](https://msdn.microsoft.com/en-us/library/ee787088(v=vs.110).aspx).

## <a name="see-also"></a>Viz také  
 [Integrované vývojové prostředí sady Visual Studio](../ide/index.md)
