---
title: Správa životního cyklu aplikací (ALM) s aplikacemi Unity | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 2dc61e63-9ba2-4c16-b1ad-f46249e576b6
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: aa36dd0f213cffa1c5f44915de6794ecc6efa0c0
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237507"
---
# <a name="application-lifecycle-management-alm-with-unity-apps"></a>Application Lifecycle Management (ALM) s aplikacemi Unity

Vývoj aplikací pro moderní platformy zahrnuje mnoho další aktivity než právě psaní kódu. Tyto aktivity, označuje jako DevOps (vývoj + operations) span úplný životní cyklus aplikace a zahrnují plánování a sledování práce, navrhování a implementace kódu, Správa úložiště zdrojového kódu spuštění sestavení, Správa nepřetržité integrace nasazení, testování (včetně testování částí a testy uživatelského rozhraní), spuštěné různé formy diagnostiky v vývoj a provozní prostředí a monitorování výkonu a uživatel chování aplikace v reálném čase pomocí telemetrie a analýzy.

 Visual Studio společně s Visual Studio Team Services a serveru Team Foundation Server poskytují řadu možností DevOps, také označované jako správa životního cyklu aplikací nebo ALM. Řada z nich se vztahují na projekty a platformy, včetně hry a dokonalé grafické aplikace vytvořené s Unity – zejména v případě, že pomocí jazyka C# jako skriptovací jazyk. Ale protože Unity má svou vlastní vývojového prostředí a modul runtime, celou řadu funkcí ALM být použity jako u jiných typů projekty vytvořené v sadě Visual Studio.

 Následující tabulky identifikuje způsob, jakým Visual Studio ALM funkce použít nebo nechcete použít při práci s Unity. Naleznete v dokumentaci propojené podrobnosti o funkce sami.

## <a name="agile-tools"></a>Nástroje pro agilní

Použití odkazu: [o agilní nástroje a Agile projektu správy](/vsts/work/backlogs/overview?view=vsts) (pomocí Visual Studio Team Services nebo sady TFS, včetně Team Explorer Everywhere)

Obecný komentář: všechny plánování a sledování funkce jsou nezávislé na kódování v jazycích jazyky a typu projektu.

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|Spravovat nevyřízené položky a sprintů|Ano||
|Sledování práce|Ano||
|Spolupráce pomocí týmové místnosti|Ano||
|Kanbanové karty|Ano||
|Vytvoření sestavy a vizualizace průběhu|Ano||

## <a name="modeling"></a>Modelování

Použití odkazu:  **[analýza a modelování architektury](../modeling/analyze-and-model-your-architecture.md)**

Obecný komentář: I když tyto funkce návrhu jsou buď bez ohledu na kódování jazyka nebo práci s jazyky rozhraní .NET, jako je C#, pracují na zlepší tradiční aplikace s hierarchií objektu a vztahy tříd. Navrhování hru v rámci Unity zahrnuje různé zlepší zcela, konkrétně vztahy grafické objekty, zvuky, shadery, skripty a tak dále. Z tohoto důvodu sady Visual Studio modelování diagram nástroje nejsou pro celý projekt Unity zvlášť důležité. Může být případně používán ke správě relací v rámci skripty jazyka C#, ale, který je součástí pouze jeden celek.

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|Sekvenční diagramy|Ne||
|Grafy závislostí|Ne||
|Hierarchie volání|Ne||
|Návrhář tříd|Ne||
|Architektura explorer|Ne||
|Diagramy UML (použijte případ, aktivity, třída, součást, pořadí a DSL)|Ne||
|Diagramy vrstev|Ne||
|Ověření vrstev|Ne||

## <a name="code"></a>Kód

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|[Použití správy verzí Team Foundation](/vsts/tfvc/overview?view=vsts) nebo Visual Studio Team Services|Ano|Unity projekty jsou jednoduše kolekce souborů, které se dají umístit do verze řízení systémů jako jiného projektu, ale existuje několik zvláštní požadavky popsané za touto tabulkou.|
|[Začínáme s Gitem v Team Services](/vsts/git/gitquickstart?view=vsts&tabs=visual-studio)|Ano|V části poznámky pod tabulkou.|
|[Zlepšení kvality kódu](../test/improve-code-quality.md)|Ano||
|[Nalezení změn kódu a další historie](../ide/find-code-changes-and-other-history-with-codelens.md)|Ano||
|[Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)|Ano||

 Zvláštní upozornění pro správu verzí s Unity:

1.  Unity sleduje metadata o herní prostředky v knihovně jeden, neprůhledné skrytá ve výchozím nastavení. Pro synchronizaci souborů a metadat, je nezbytné, chcete-li zobrazit metadata a uložit v dalších spravovatelných blocích. Podrobnosti najdete v části [pomocí systémy řízení externí verze se Unity](http://docs.unity3d.com/Manual/ExternalVersionControlSystemSupport.html) (Unity dokumentaci).

2.  Ne všechny soubory a složky v projektu Unity jsou vhodné pro řízení zdroje, jako je také popsáno v výše uvedený odkaz. Prostředky a ProjectSettings složky musí být přidaní, ale knihovny a dočasné složky neměli. Doplňkový seznam generované soubory, které by přejděte do správy zdrojového kódu, najdete v části diskuse [použití Git pro Unity3D zdrojového kódu?](http://stackoverflow.com/questions/18225126/how-to-use-git-for-unity3d-source-control) v zásobníku. Celá řada vývojářů mít také rozsáhlý blok na toto téma nezávisle.

3.  Binární prostředky v projektu Unity – například textury nebo zvukové soubory, může trvat až velké množství úložiště. Různé systémy správy zdrojového jako Git ukládat jedinečnou kopii souboru pro každé změně, která se i v případě, že tato změna ovlivňuje pouze malou část souboru. To může způsobit opakovaném úložiště Git. Chcete-li vyřešit tím, Unity vývojáři často zvolit, aby byla pouze poslední prostředky přidat do jejich úložiště a použít jiný způsob dosavadní práce jejich prostředků, jako je například OneDrive, DropBox nebo git přílohy. Tento přístup funguje, protože tyto prostředky většinou nemusí být verzí společně s změny zdrojového kódu. Vývojáři také běžně nastavit režim serializace Asset editoru projektu na Force Text k ukládání souborů scény v textu, ne binární formát, který umožňuje sloučení ve správě zdrojového kódu. Podrobnosti najdete v tématu [nastavení editoru](http://docs.unity3d.com/Manual/class-EditorManager.html) (Unity dokumentaci).

## <a name="build"></a>Sestavení
 Použití odkazu:  **[sestavení a verze](/vsts/build-release/index)**

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|Na místním serveru TFS|Možné|Unity projekty jsou vytvořeny pomocí prostředí Unity a ne prostřednictvím sady Visual Studio sestavení systému (vytváření v rámci sady Visual Studio Tools pro Unity bude zkompilovat skripty, ale není vytvoření spustitelného souboru). Je možné [Unity projekty z příkazového řádku sestavení](http://docs.unity3d.com/Manual/CommandLineArguments.html) (Unity dokumentace), takže je možné konfigurovat MSBuild proces na serveru TFS provést odpovídající Unity příkazy, za předpokladu, že Unity samotné je nainstalován na Tento počítač.<br /><br /> Také nabízí Unity [Unity cloudu sestavení](https://build.cloud.unity3d.com/landing/), který sleduje úložiště Git nebo SVN a spustí pravidelné sestavení. V současné době ale nefunguje s verzí Team Foundation nebo Visual Studio Team Services.|
|Místní sestavení server propojený s Visual Studio Team Services|Možné|Zadaný stejných podmínek jako výše je další možné směrovat sestavení vyvolané prostřednictvím Visual Studio Team Services pomocí sady TFS počítače místně.  V tématu [sestavení a verzí agentů](/vsts/build-release/concepts/agents/agents) pokyny.|
|Hostované řadič služby Visual Studio Team Services|Ne|V současné době se nepodporují Unity sestavení.|
|Vytváření definic s před a po skripty|Ano|Definici vlastní sestavení, která používá ke spuštění sestavení příkazového řádku Unity můžete také nakonfigurovat pro skripty před a po sestavení.|
|Průběžnou integraci včetně ověřované vrácení se změnami|Ano|Ověřované vrácení vrácení se změnami pro TFVC pouze jako Git funguje na žádost o přijetí změn modelu, nikoli vrácení se změnami.|

## <a name="testing"></a>Testování

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|Plánování testů, vytváření testovacích případů a uspořádání testovacích sad|Ano||
|Manuální testování|Ano||
|Nástroje Test Manager (záznam a přehrávání testů)|Zařízení s Windows a Androidem emulátorů pouze||
|Pokrytí kódu|není k dispozici|Není k dispozici jako jednotka testování se stane, v rámci Unity a není Visual Studio, najdete níže.|
|[Testování částí kódu](../test/unit-test-your-code.md)|V rámci Unity, ale ne Visual Studio|Poskytuje Unity vlastní jednotkové testování framework jako součást [nástroje Test Unity](https://www.assetstore.unity3d.com/en/#!/content/13802) (Unity Asset úložiště). Výsledky testů jednotek jsou hlášeny v rámci Unity a nebude prezentované v sadě Visual Studio.|
|[Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)|Ne|Programové testy uživatelského rozhraní závisí na čitelný ovládací prvky v uživatelském rozhraní aplikace; Aplikace Unity jsou grafické ve své podstatě a obsah není tak přečíst nástroje uživatelského rozhraní programového testu.|

## <a name="improve-code-quality"></a>Zlepšení kvality kódu

Použití odkazu:  **[zlepšení kvality kódu](../test/improve-code-quality.md)**

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|[Analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Ano|Kód skriptu jazyka C# v sadě Visual Studio můžete analyzovat.|
|[Hledání duplicitního kódu pomocí zjišťování klonu kódu](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Ano|Kód skriptu jazyka C# v sadě Visual Studio můžete analyzovat.|
|[Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Ano|Kód skriptu jazyka C# v sadě Visual Studio můžete analyzovat.|
|[Prohlížeč výkonu](../profiling/performance-explorer.md)|Ne|Použití [Unity profileru](http://docs.unity3d.com/Manual/Profiler.html) (Unity webu).|
|[Analýza problémů s pamětí rozhraní .NET Framework](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Ne|Nástroje sady Visual Studio nemusí háky do Mono framework (jako je použité ve Unity) pro vytváření profilů. Použití [Unity profileru](http://docs.unity3d.com/Manual/Profiler.html) (Unity dokumentaci).|

## <a name="release-management"></a>Správa vydaných verzí

Použití odkazu: [sestavení a verze – přehled](/vsts/pipelines/overview?view=vsts)

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|Správa procesů verzí|Ano||
|Nasazení na servery pro zkušební načtení prostřednictvím skriptů|Ano||
|Nahrajte do obchodu s aplikacemi|Částečné|Rozšíření jsou k dispozici, můžete automatizovat tohoto procesu pro některé obchody s aplikacemi.  V tématu [rozšíření pro Visual Studio Team Services](https://marketplace.visualstudio.com/VSTS), například [rozšíření pro Google Play](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|

## <a name="monitor-with-hockeyapp"></a>Monitorování s HockeyApp

Použití odkazu:  **[monitorování s HockeyApp](https://www.hockeyapp.net/features/)**

|Funkce|Podporované s Unity|Další komentáře|
|-------------|--------------------------|-------------------------|
|K chybě analýzy, telemetrie a beta rozdělení|Ano|HockeyApp je užitečné hlavně pro zpracování beta rozdělení a získání sestavy havárií.<br /><br /> Pro telemetrie z skripty jazyka C# je možné použít libovolnou architekturu analytics za předpokladu, že běží na verzi rozhraní .NET, který je používán Unity. To umožňuje však pro analýzu pouze v rámci herní skripty a není hlubšímu uvnitř modul Unity. V současné době není k dispozici žádný modul plug-in pro Application Insights, ale modulů plug-in, jako jsou k dispozici pro jiné řešení pro analýzu [Unity Analytics](https://www.assetstore.unity3d.com/en/#!/content/28120) a [Google Analytics](https://github.com/googleanalytics/google-analytics-plugin-for-unity). Služby jako Unity analýzy, které pochopení povahy projektu Unity bude samozřejmě poskytují mnohem víc smysluplný analysis než obecné rozhraní.|