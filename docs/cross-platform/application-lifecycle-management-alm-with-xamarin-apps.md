---
title: Správa životního cyklu aplikací (ALM) s aplikacemi Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: ff978cc2-5a25-46d6-921b-e51adaa65992
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: f44ad3a7c44f9de592d3b4d4add261fca74f5c39
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281297"
---
# <a name="application-lifecycle-management-alm-with-xamarin-apps"></a>Správa životního cyklu aplikací s aplikacemi Xamarin

Xamarin umožňuje vytvářet cílené na Android, iOS a Windows pomocí jazyka C# .NET a Visual Studio mobilní aplikace a platformy. Xamarin umožňuje velkou část kódu být sdílen mezi platformami s pouze malým procentem museli být specifické pro platformu. Další informace o Xamarin sám sebe, najdete v části [Visual Studio a Xamarin](../cross-platform/visual-studio-and-xamarin.md).

Vývoj aplikací pro moderní platformy zahrnuje mnoho další aktivity než právě psaní kódu. Tyto aktivity, označuje jako DevOps (vývoj + operations), span úplný životní cyklus aplikace a zahrnují plánování a sledování práce, navrhování a implementace kódu, Správa úložiště zdrojového kódu spuštění sestavení, Správa nepřetržité integrace nasazení, testování (včetně testování částí a testy uživatelského rozhraní), spuštěné různé formy diagnostiky v vývoj a provozní prostředí a monitorování výkonu a uživatel chování aplikace v reálném čase pomocí telemetrie a analýzy.

Visual Studio společně s Visual Studio Team Services a serveru Team Foundation Server poskytují řadu možností DevOps, také označované jako správa životního cyklu aplikací nebo ALM. Mnoho z těchto se zcela vztahují na projekty napříč platformami.

To platí hlavně s aplikacemi Xamarin vzhledem k tomu, že jsou integrované s C# a rozhraní .NET, kolem které některé ALM jsou integrované nástroje. Jiné nástroje, vyžadují úzkou integraci s buildu a běhového prostředí. Protože aplikace Xamarin spustit na jiných platforem než Windows a použít Mono implementace rozhraní .NET, Xamarin poskytuje specializované nástroje pro určité potřebuje.

Následující tabulky identifikuje funkce, které Visual Studio ALM můžete předpokládat fungují dobře u projektu Xamarin, a ty, které mají omezení. Naleznete v dokumentaci propojené podrobnosti o funkce sami.

## <a name="agile-tools"></a>Nástroje pro agilní

Použití odkazu:  **[o agilní nástroje a Agile projektu správy](/vsts/work/backlogs/overview?view=vsts)**

Obecný komentář: všechny plánování a sledování funkce jsou nezávislé na kódování v jazycích jazyky a typu projektu.

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|Spravovat nevyřízené položky a sprintů|Ano||
|Sledování práce|Ano||
|Spolupráce pomocí týmové místnosti|Ano||
|Kanbanové karty|Ano||
|Vytvoření sestavy a vizualizace průběhu|Ano||

## <a name="modeling"></a>Modelování

Použití odkazu:  **[analýza a modelování architektury](../modeling/analyze-and-model-your-architecture.md)**

Funkce návrhu jsou nezávislé na kódování jazyka nebo pracovat s jazyky rozhraní .NET, jako je C#. V tématu [role architektura a modelování diagramů v Software Development](../modeling/scenario-change-your-design-using-visualization-and-modeling.md#ModelingDiagramsTools) pro které aspekty se vztahují ke kódu.

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|Sekvenční diagramy|Ano||
|Grafy závislostí|Ano||
|Hierarchie volání|Ano||
|Návrhář tříd|Ano||
|Architektura explorer|Ano||
|Diagramy UML (použijte případ, aktivity, třída, součást, pořadí a DSL)|Ano||
|Diagramy vrstev|Ano||
|Ověření vrstev|Ano||

## <a name="code"></a>Kód

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|[Použití správy verzí Team Foundation](/vsts/tfvc/overview?view=vsts) nebo Visual Studio Team Services|Ano||
|[Začínáme s Gitem v Team Services](/vsts/git/gitquickstart?view=vsts&tabs=visual-studio)|Ano||
|[Zlepšení kvality kódu](../test/improve-code-quality.md)|Ano||
|[Nalezení změn kódu a další historie](../ide/find-code-changes-and-other-history-with-codelens.md)|Ano|S výjimkou napříč hranicemi specifické pro platformu, kde není vyřešený implementace až při spuštění.|
|[Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)|Ano||

## <a name="build"></a>Sestavení

Použití odkazu:  **[sestavení a verze](/vsts/pipelines/index?view=vsts)**

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|Na místním serveru TFS|Ano|Sestavení počítače musí mít nainstalovaný Xamarin a může být propojený na OSX počítači pro vývoj pro iOS. V tématu [použít TFVC](/vsts/tfvc/overview?view=vsts)|
|Místní sestavení server propojený s Visual Studio Team Services|Ano|V tématu [sestavení a verzí agentů](/vsts/pipelines/agents/agents?view=vsts) pokyny.|
|Hostované řadič služby Visual Studio Team Services|Ano|V tématu [sestavení vaší aplikace Xamarin](/vsts/pipelines/apps/mobile/xamarin?view=vsts&tabs=vsts).|
|Vytváření definic s před a po skripty|Ano||
|Průběžnou integraci včetně ověřované vrácení se změnami|Ano|Ověřované vrácení vrácení se změnami pro TFVC pouze jako Git funguje na žádost o přijetí změn modelu, nikoli vrácení se změnami.|

## <a name="test"></a>Test

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|Plánování testů, vytváření testovacích případů a uspořádání testovacích sad|Ano||
|Manuální testování|Ano||
|Nástroje Test Manager (záznam a přehrávání testů)|Ano|Zařízení se systémem Windows a Androidem emulátorů pouze ze sady Visual Studio. Záznam pro všechna zařízení je možné s [Xamarin testu záznamník](/appcenter/test-cloud/uitest/).|
|Pokrytí kódu|není k dispozici||
|[Testování částí kódu](../test/unit-test-your-code.md)|Ano|Pro systém Windows a Androidem cíle lze použít integrované nástroje Mstestu. Xamarin pro spouštění testů jednotek v systému Windows, Android a iOS, doporučuje NUnit. V tématu [použít TFVC](/vsts/tfvc/overview?view=vsts).|
|[Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)|Pouze v systému Windows|Zapisovač testu uživatelského rozhraní sady Visual Studio je pouze v systému Windows. Všechny platformy, najdete v části [Xamarin.UITest](/appcenter/test-cloud/uitest/).|

## <a name="improve-code-quality"></a>Zlepšení kvality kódu

Použití odkazu:  **[zlepšení kvality kódu](../test/improve-code-quality.md)**

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|[Analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Ano||
|[Hledání duplicitního kódu pomocí zjišťování klonu kódu](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Ano||
|[Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Ano||
|[Prohlížeč výkonu](../profiling/performance-explorer.md)|Ne|Použití [Xamarin profileru](/xamarin/cross-platform/deploy-test/) prostřednictvím Xamarin Studio místo. Všimněte si, že profileru Xamarin je aktuálně ve verzi preview a zatím nefunguje pro Windows cíle.|
|[Analýza problémů s pamětí rozhraní .NET Framework](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Ne|Nástroje sady Visual Studio nemusí háky do Mono rozhraní pro profilaci.|

## <a name="release-management"></a>Správa vydaných verzí

Použití odkazu:  **[sestavení a verzí v služby VSTS a TFS](/vsts/pipelines/overview?view=vsts)**

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|Správa procesů verzí|Ano||
|Nasazení na servery pro zkušební načtení prostřednictvím skriptů|Ano||
|Nahrajte do obchodu s aplikacemi|Částečné|Rozšíření jsou k dispozici, můžete automatizovat tohoto procesu pro některé obchody s aplikacemi.  V tématu [rozšíření pro Visual Studio Team Services](https://marketplace.visualstudio.com/VSTS), například [rozšíření pro Google Play](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|

## <a name="monitor-with-hockeyapp"></a>Monitorování s HockeyApp

Použití odkazu:  **[monitorování s HockeyApp](https://www.hockeyapp.net/features/)**

|Funkce|Podporované xamarinu|Další komentáře|
|-------------|----------------------------|-------------------------|
|K chybě analýzy, telemetrie a beta rozdělení|Ano||