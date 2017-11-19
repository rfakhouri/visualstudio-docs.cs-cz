---
title: "Správa životního cyklu aplikací (ALM) s aplikacemi Xamarin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff978cc2-5a25-46d6-921b-e51adaa65992
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 41fe8afba19939dfbbbd5c055f5ebd53e9fc2e04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="application-lifecycle-management-alm-with-xamarin-apps"></a>Správa životního cyklu aplikací (ALM) s aplikacemi Xamarin
Xamarin umožňuje vytvářet cílené na Android, iOS a Windows pomocí jazyka C# .NET a Visual Studio mobilní aplikace a platformy. Xamarin umožňuje velkou část kódu být sdílen mezi platformami s pouze malým procentem museli být specifické pro platformu. Další informace o Xamarin sám sebe, najdete v části [Visual Studio a Xamarin](../cross-platform/visual-studio-and-xamarin.md).  
  
 Vývoj aplikací pro moderní platformy zahrnuje mnoho další aktivity než právě psaní kódu. Tyto aktivity, označuje jako DevOps (vývoj + operations), span úplný životní cyklus aplikace a zahrnují plánování a sledování práce, navrhování a implementace kódu, Správa úložiště zdrojového kódu spuštění sestavení, Správa nepřetržité integrace nasazení, testování (včetně testování částí a testy uživatelského rozhraní), spuštěné různé formy diagnostiky v vývoj a provozní prostředí a monitorování výkonu a uživatel chování aplikace v reálném čase pomocí telemetrie a analýzy.  
  
 Visual Studio společně s Visual Studio Team Services a serveru Team Foundation Server poskytují řadu možností DevOps, také označované jako správa životního cyklu aplikací nebo ALM. Mnoho z těchto se zcela vztahují na projekty napříč platformami.  
  
 To platí hlavně s aplikacemi Xamarin vzhledem k tomu, že jsou integrované s C# a rozhraní .NET, kolem které některé ALM jsou integrované nástroje. Jiné nástroje, vyžadují úzkou integraci s buildu a běhového prostředí. Protože aplikace Xamarin spustit na jiných platforem než Windows a použít Mono implementace rozhraní .NET, Xamarin poskytuje specializované nástroje pro určité potřebuje.  
  
 Následující tabulky identifikuje funkce, které Visual Studio ALM můžete předpokládat fungují dobře u projektu Xamarin, a ty, které mají omezení. Naleznete v dokumentaci propojené podrobnosti o funkce sami.  
  
## <a name="agile-tools"></a>Nástroje pro agilní  
 Použití odkazu:  **[pracovní](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)**  (pomocí Visual Studio Team Services nebo sady TFS, včetně Team Explorer Everywhere)  
  
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
|[Použití správy verzí Team Foundation](http://msdn.microsoft.com/Library/1d629052-c65d-4c5d-81eb-eaa4413fe285) nebo Visual Studio Team Services|Ano||  
|[Začínáme s Gitem v Team Services](http://msdn.microsoft.com/Library/32f46ecd-1b03-4ef0-a9c4-8a120da2b03f)|Ano||  
|[Zlepšení kvality kódu](/visualstudio/test/improve-code-quality)|Ano||  
|[Nalezení změn kódu a další historie](../ide/find-code-changes-and-other-history-with-codelens.md)|Ano|S výjimkou napříč hranicemi specifické pro platformu, kde není vyřešený implementace až při spuštění.|  
|[Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)|Ano||  
  
## <a name="build"></a>Sestavení  
 Použití odkazu:  **[sestavení](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)**  
  
|Funkce|Podporované xamarinu|Další komentáře|  
|-------------|----------------------------|-------------------------|  
|Na místním serveru TFS|Ano|Sestavení počítače musí mít nainstalovaný Xamarin a může být propojený na OSX počítači pro vývoj pro iOS. V tématu [konfigurace sady TFS pro Xamarin](http://developer.xamarin.com/guides/cross-platform/ci/configuring_tfs/) (Xamarin webu)|  
|Místní sestavení server propojený s Visual Studio Team Services|Ano|V tématu [sestavení serveru](http://msdn.microsoft.com/Library/2d258a0a-f178-4e93-9da1-eba61151af3c) pokyny.|  
|Hostované řadič služby Visual Studio Team Services|Ano|V tématu [sestavení vaší aplikace Xamarin](https://www.visualstudio.com/en-us/docs/build/apps/mobile/xamarin).|  
|Vytváření definic s před a po skripty|Ano||  
|Průběžnou integraci včetně ověřované vrácení se změnami|Ano|Ověřované vrácení vrácení se změnami pro TFVC pouze jako Git funguje na žádost o přijetí změn modelu, nikoli vrácení se změnami.|  
  
## <a name="testing"></a>Testování  
 Použití odkazu:  **[testování aplikace](/devops-test-docs/test/test-apps-early-and-often)**  
  
|Funkce|Podporované xamarinu|Další komentáře|  
|-------------|----------------------------|-------------------------|  
|Plánování testů, vytváření testovacích případů a uspořádání testovacích sad|Ano||  
|Manuální testování|Ano||  
|Nástroje Test Manager (záznam a přehrávání testů)|Ano|Zařízení se systémem Windows a Androidem emulátorů pouze ze sady Visual Studio. Záznam pro všechna zařízení je možné s [Xamarin testu záznamník](https://www.xamarin.com/test-cloud/recorder).|  
|Pokrytí kódu|není k dispozici||  
|[Testování částí kódu](../test/unit-test-your-code.md)|Ano|Pro systém Windows a Androidem cíle lze použít integrované nástroje Mstestu. Xamarin pro spouštění testů jednotek v systému Windows, Android a iOS, doporučuje NUnit. V tématu [konfigurace sady TFS pro Xamarin](http://developer.xamarin.com/guides/cross-platform/ci/configuring_tfs/) (Xamarin webu).|  
|[Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)|Pouze v systému Windows|Zapisovač testu uživatelského rozhraní sady Visual Studio je pouze v systému Windows. Všechny platformy, najdete v části [Xamarin testu záznamník](https://www.xamarin.com/test-cloud/recorder).|  
  
## <a name="improve-code-quality"></a>Zlepšení kvality kódu  
 Použití odkazu:  **[zlepšení kvality kódu](/visualstudio/test/improve-code-quality)**  
  
|Funkce|Podporované xamarinu|Další komentáře|  
|-------------|----------------------------|-------------------------|  
|[Analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Ano||  
|[Hledání duplicitního kódu pomocí zjišťování klonu kódu](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Ano||  
|[Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Ano||  
|[Prohlížeč výkonu](../profiling/performance-explorer.md)|Ne|Použití [Xamarin profileru](http://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/) prostřednictvím Xamarin Studio místo. Všimněte si, že profileru Xamarin je aktuálně ve verzi preview a zatím nefunguje pro Windows cíle.|  
|[Analýza problémů s pamětí rozhraní .NET Framework](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Ne|Nástroje sady Visual Studio nemusí háky do Mono rozhraní pro profilaci.|  
  
## <a name="release-management"></a>Správa vydaných verzí  
 Použití odkazu:  **[automatizace nasazování pomocí správy verzí](https://msdn.microsoft.com/library/vs/alm/release/overview)**  
  
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