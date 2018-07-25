---
title: Správa životního cyklu aplikací (ALM) s aplikacemi Xamarin | Dokumentace Microsoftu
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
ms.openlocfilehash: b711c6c67eb7466d642048f2546c532b9b2e2926
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231853"
---
# <a name="application-lifecycle-management-alm-with-xamarin-apps"></a>Správa životního cyklu aplikací s aplikacemi Xamarin

Xamarin umožňuje vytvářet multiplatformní mobilní aplikace cílí na Android, iOS a Windows pomocí C#, .NET a Visual Studio. Xamarin umožňuje velkou část kódu sdílet mezi platformami s pouze malým procentem museli být specifické pro platformu. Další informace o Xamarinu, sama, naleznete v tématu [Visual Studio a Xamarin](../cross-platform/visual-studio-and-xamarin.md).

Vývoj aplikací pro moderní platformy zahrnuje mnoho aktivit více než jen psaní kódu. Tyto aktivity, označuje jako span kompletní životní cyklus aplikace DevOps (vývoj + operations) a zahrnují plánování a sledování práce, navrhování a implementace kódu, správu úložiště zdrojového kódu, běžících sestavení, Správa průběžné integrace nasazení, testování (včetně jednotkové testy a testy uživatelského rozhraní), spuštění různé formy diagnostiku ve vývojovém a produkčním prostředí a sledování výkonu a uživatel chování aplikací v reálném čase prostřednictvím telemetrie a analýz.

Visual Studio spolu s Visual Studio Team Services a Team Foundation Server poskytuje širokou škálu možnosti DevOps, také označuje jako správa životního cyklu aplikací nebo ALM. Mnohé z nich jsou zcela použitelná pro multiplatformní projekty.

To platí zejména s aplikacemi Xamarin vzhledem k tomu, že tyto šablony jsou sestaveny pomocí jazyka C# a .NET, po které některé ALM jsou integrované nástroje. Další nástroje, vyžaduje úzkou integraci s buildu a běhového prostředí. Protože aplikace spustit na platformách než Windows a Xamarin používat Mono implementaci rozhraní .NET, Xamarin poskytuje pro určité vyžaduje specializované nástroje.

V tabulce dole najdete identifikuje funkcí, které Visual Studio ALM můžete očekávat fungovat dobře si projekt Xamarin a ty, které mají omezení. Naleznete v dokumentaci propojené informace o funkcích, sami.

## <a name="agile-tools"></a>Agilní nástroje

Referenční odkaz:  **[o agilní nástroje a agilní řízení projektů](/vsts/work/backlogs/overview?view=vsts)**

Obecné komentáře: všechny plánování a sledování funkce jsou nezávislé na typu projektu a kódování jazyky.

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|Správa nevyřízených položek a sprintů|Ano||
|Sledování práce|Ano||
|Spolupráce pomocí týmové místnosti|Ano||
|Kanbanové Tabule|Ano||
|Sestavy a vizualizace průběhu|Ano||

## <a name="modeling"></a>Modelování

Referenční odkaz:  **[analyzovat a architektura modelu](../modeling/analyze-and-model-your-architecture.md)**

Funkce pro návrh platí bez ohledu na programovací jazyk, nebo pracovat s jazyky .NET, jako je C#. Zobrazit [role architektury a modelování diagramů při vývoji softwaru](../modeling/scenario-change-your-design-using-visualization-and-modeling.md#ModelingDiagramsTools) pro jaké aspekty se vztahují ke kódu.

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|Sekvenční diagramy|Ano||
|Grafy závislostí|Ano||
|Hierarchie volání|Ano||
|Návrhář tříd|Ano||
|Průzkumník architektury|Ano||
|Diagramy UML (použití případu, aktivit, třídy, komponenty, pořadí a DSL)|Ano||
|Diagramy vrstev|Ano||
|Ověření vrstvy|Ano||

## <a name="code"></a>Kód

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|[Použití správy verzí Team Foundation](/vsts/tfvc/overview?view=vsts) nebo Visual Studio Team Services|Ano||
|[Začínáme s úložištěm Git ve službě Team Services](/vsts/git/gitquickstart?view=vsts&tabs=visual-studio)|Ano||
|[Zlepšení kvality kódu](../test/improve-code-quality.md)|Ano||
|[Nalezení změn kódu a další historie](../ide/find-code-changes-and-other-history-with-codelens.md)|Ano|S výjimkou napříč hranicemi specifické pro platformu, kde implementace není vyřešený až do spuštění.|
|[Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)|Ano||

## <a name="build"></a>Sestavení

Referenční odkaz:  **[sestavení a vydání](/vsts/pipelines/index?view=vsts)**

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|Na místním serveru TFS|Ano|Počítače sestavení musí mít nainstalovaný Xamarin a lze propojit na OSX počítač pro vývoj pro iOS. Zobrazit [můžete používat TFVC](/vsts/tfvc/overview?view=vsts)|
|Místní server sestavení propojené s Visual Studio Team Services|Ano|Zobrazit [agenti sestavení a vydání](/vsts/pipelines/agents/agents?view=vsts) pokyny.|
|Hostovaný kontroler služby Visual Studio Team Services|Ano|Zobrazit [sestavení vaší aplikace Xamarin](/vsts/pipelines/apps/mobile/xamarin?view=vsts&tabs=vsts).|
|Vytvoření definice s předběžné a pozálohovacích skriptů|Ano||
|Průběžná integrace, včetně hlídané vrácení se změnami se|Ano|Ověřované vrácení se změnami se pro TFVC pouze, jak Git funguje na modelu žádosti o přijetí změn spíše než vrácení se změnami.|

## <a name="test"></a>Test

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|Plánování testů, vytváření testovacích případů a uspořádání testovacích sad|Ano||
|Manuální testování|Ano||
|Test Manager (záznam a přehrávání testů)|Ano|Zařízení Windows a emulátory Androidu jenom ze sady Visual Studio. Záznam pro všechna zařízení je možné s [Xamarin Test Recorder](/appcenter/test-cloud/uitest/).|
|Pokrytí kódu|není k dispozici||
|[Testování částí kódu](../test/unit-test-your-code.md)|Ano|Pro Windows a cílech Android je možné integrované nástroje MSTest. Xamarin pro spuštění testů jednotek pro Windows, Android a iOS, doporučuje NUnit. Zobrazit [můžete používat TFVC](/vsts/tfvc/overview?view=vsts).|
|[Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)|Pouze Windows|Rekordér testu uživatelského rozhraní sady Visual Studio je jenom pro Windows. Pro všechny platformy, najdete v článku [Xamarin.UITest](/appcenter/test-cloud/uitest/).|

## <a name="improve-code-quality"></a>Zlepšení kvality kódu

Referenční odkaz:  **[zlepšení kvality kódu](../test/improve-code-quality.md)**

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|[Analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Ano||
|[Hledání duplicitního kódu pomocí zjišťování klonování kódu](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Ano||
|[Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Ano||
|[Prohlížeč výkonu](../profiling/performance-explorer.md)|Ne|Použití [Xamarin Profiler](/xamarin/cross-platform/deploy-test/) přes Xamarin Studio místo. Všimněte si, že Xamarin Profiler je aktuálně ve verzi preview a ještě nefunguje pro Windows cíle.|
|[Analýza problémů paměti rozhraní .NET Framework](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Ne|Nástroje sady Visual Studio nemusí háky do Mono framework pro profilování.|

## <a name="release-management"></a>Správa vydaných verzí

Referenční odkaz:  **[buildu a verze ve VSTS a TFS](/vsts/pipelines/overview?view=vsts)**

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|Správa procesů vydávání verzí|Ano||
|Nasazení na servery pro zkušební načtení pomocí skriptů|Ano||
|Nahrát do app storu|Částečné|Rozšíření jsou k dispozici, který tento proces pro některé obchody automatizovat.  Zobrazit [rozšíření pro Visual Studio Team Services](https://marketplace.visualstudio.com/VSTS), například [rozšíření pro Google Play](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|

## <a name="monitor-with-hockeyapp"></a>Monitorování pomocí aplikace HockeyApp

Referenční odkaz:  **[monitorování pomocí aplikace HockeyApp](https://www.hockeyapp.net/features/)**

|Funkce|Nepodporuje se Xamarinem|Další komentáře|
|-------------|----------------------------|-------------------------|
|K chybě analýzy, telemetrie a beta rozdělení|Ano||