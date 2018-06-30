---
title: Profilace výkonu aplikací služby SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Profiling.SilverlightWebPartOnly
- VS.SharePointTools.Profiling.DotNetTrustLevel
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, profiling
- performance testing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, performance testing
- profiling [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7fc119bbd990dab11a144ccc4e1894bb827a2fe1
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118051"
---
# <a name="profile-the-performance-of-sharepoint-applications"></a>Profil výkonu aplikací služby SharePoint

Pokud vaše aplikace služby SharePoint se provádí pomalu nebo neefektivnímu, slouží k identifikaci problematické kódu a další elementy profilování funkce v sadě Visual Studio. Pomocí testování funkce zatížení, můžete určit, jakým způsobem aplikace SharePoint provádí vytížený, například když mnoho uživatelů současně přístup k aplikaci. Spuštěním testů výkonnosti webu budete vyhodnocovat, jakým způsobem aplikace provádí na webu. Pomocí programových testů uživatelského rozhraní, můžete ověřit, zda celou aplikaci služby SharePoint, včetně jeho uživatelské rozhraní, funguje správně. Použijete-li tyto testy společně, mohou pomoci identifikovat problémy s výkonem, před nasazením aplikace.

## <a name="profile-tools-overview"></a>Přehled nástrojů pro profil

Profilace odkazuje na proces sledování a zaznamenávání výkonu chování aplikace při jeho spuštění. Podle profilace aplikace, můžete odkrýt problémy, třeba kritická místa, neefektivní kód a problémy přidělení paměti, které způsobit selhání aplikací pracovat pomalu nebo použít příliš mnoho paměti. Například můžete profilace k identifikaci hotspotům ve vašem kódu, které jsou segmenty kódu, které se často nazývají a může zpomalit celkový výkon vaší aplikace. Po identifikaci hotspotům, můžete často optimalizovat nebo je odstranit.

Několik nástrojů pro profilaci v integrované vývojové prostředí (IDE) slouží k identifikaci a najděte tyto druhy problémů s výkonem. Tyto nástroje fungovat stejným způsobem jako pro projekty SharePoint, stejně jako u jiných typů projektů sady Visual Studio. Průvodce profilace výkonu nástrojů pro vás provede Vytvoření výkonnostní relace, který používá testy, které zadáte. Výkonnostní relace je sada konfiguračních dat, který se používá pro shromažďování informací o výkonu z aplikace, spolu s výsledky jeden nebo více profilování spustí. Výkonnostní relace jsou uložené ve složce projektu a lze je zobrazit v **prohlížeč výkonu**. Další informace najdete v tématu [metody kolekce údajů o výkonu Principy](/visualstudio/profiling/understanding-performance-collection-methods).

Po vytvoření a spuštění profilu analýzy ve vaší aplikaci, sestava obsahuje podrobné informace o jeho výkon. Tato sestava může být položky jako např graf využití procesoru určitou dobu, hierarchické funkce zásobník volání nebo volání stromu. Přesný obsah sestavy se může lišit v závislosti na typu test, který spouštíte, jako je například vzorkování nebo instrumentace. Další informace najdete v tématu [přehled sestavy nástrojů pro profilaci](http://go.microsoft.com/fwlink/?LinkId=224689).

## <a name="performance-session-process"></a>Proces relace výkonu

Do profilu aplikace, můžete spustit pomocí Průvodce profilace výkonu nástrojů pro vytvoření relace výkonu. Na řádku nabídek zvolte **analyzovat**, **spusťte Průvodce výkonu**. Po dokončení průvodce, je třeba zadat požadované informace pro relaci výkonu, jako je například metoda profil, který chcete a aplikace, které chcete profil. Další informace najdete v tématu [postup: profilu webové stránky nebo webové aplikace pomocí průvodcem výkonu](http://go.microsoft.com/fwlink/?LinkId=224692). Jako alternativu můžete použít možnosti příkazového řádku nastavit a spustit relaci výkonu. Další informace najdete v tématu [pomocí profilace nástroje z příkazového řádku](http://go.microsoft.com/fwlink/?LinkId=224703). Pokud chcete ručně nakonfigurovat každý aspekt výkonu relace, najdete v části [postupy: ruční vytváření výkonnostních relací s nástroji pro profilaci](http://go.microsoft.com/fwlink/?LinkId=224691). Můžete také vytvořit relaci výkonu z testů jednotek, v **výsledky testu** okně otevírání místní nabídku pro testování částí a pak vyberete **vytvořit relaci výkonu**.

Po nastavení výkonnostní relace je uložit konfiguraci relace, server je nakonfigurován k poskytování data profilování a spuštění aplikace. Při používání aplikace, data výkonu se zapisují do souboru protokolu. Výkonnostní relace jsou uvedeny v **prohlížeč výkonu** pod **cíle** složky. Po dokončení výkonnostní relace jeho sestavy se zobrazí v **sestavy** složky v **prohlížeč výkonu**. Chcete-li zobrazit sestavu, otevřete ho v **prohlížeč výkonu**. Chcete-li zobrazit nebo konfigurovat vlastnosti výkonnostní relace, otevřete jeho místní nabídky v **prohlížeč výkonu**a potom zvolte **vlastnosti**. Další informace o určité vlastnosti výkonu Relace najdete v tématu [konfigurace výkonnostních relací pro nástroje pro profilaci](http://go.microsoft.com/fwlink/?LinkId=224694). Informace o tom, jak interpretovat výsledky výkonnostní relace najdete v tématu [analýza dat nástrojů pro profilaci](http://go.microsoft.com/fwlink/?LinkId=224704).

## <a name="stress-test"></a>Zátěžový test

Vytvořením zátěžových testů a testy výkonnosti webu v sadě Visual Studio můžete analyzovat výkon přízvuk aplikací. Když vytvoříte zátěžový test v sadě Visual Studio, určíte kombinace faktorů, scénář, aplikaci otestovat s názvem. Tyto faktory zahrnují vzor zatížení, model kombinace testů, kombinace testů, poměr sítí a kombinace webového prohlížeče. Scénářů zátěžových testů můžete zahrnout testy částí a testy výkonu webu.

Obrázek 1: Zátěžové testování výsledků příklad

![Probíhá test zatížení grafech zobrazení](../sharepoint/media/load-webgraphs.png "zobrazení grafech spuštění zátěžového testu")

Testy výkonnosti webu simulaci, jak koncový uživatel může komunikovat s aplikace SharePoint. Testy výkonnosti webu můžete vytvořit zaznamenáním požadavků HTTP v relaci prohlížeče nebo pomocí **zapisovač testu výkonu webu**. Zobrazí webové požadavky v **Editor testu výkonnosti webu** po dokončení relace prohlížeče. Potom můžete ladit výsledky v **prohlížeč výsledků testu výkonnosti webu**. Testy výkonnosti webu můžete vytvořit také ručně pomocí **Editor testu výkonnosti webu**.

## <a name="test-user-interfaces"></a>Testování uživatelského rozhraní

Programové testy uživatelského rozhraní automaticky jednotky aplikace SharePoint jeho uživatelském rozhraní (UI). Tyto testy tématech ovládacích prvků uživatelského rozhraní, jako je například tlačítka a nabídky, chcete-li ověřit, že fungují správně. Tento druh testování je obzvláště užitečné, pokud se ověření nebo jiné logiky provádí v uživatelském rozhraní, například na webové stránce. Programové testy uživatelského rozhraní můžete použít také k automatizaci manuálních testů. Vytváříte programové testy uživatelského rozhraní pro vaše aplikace SharePoint stejným způsobem, jako je vytváření testů pro jiné typy aplikací. Další informace najdete v tématu [testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní](/visualstudio/test/testing-sharepoint-2010-applications-with-coded-ui-tests).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Návod: Profil aplikace SharePoint](../sharepoint/walkthrough-profiling-a-sharepoint-application.md)|Demonstruje postup proveďte v aplikace SharePoint analýzu profil vzorkování.|
|[Testování výkonu aplikace před verzí](/vsts/test/load-test/run-performance-tests-app-before-release?view=vsts)|Popisuje, jak vytvořit zátěžové testy, které vám pomůžou aplikací služby SharePoint zátěžový test.|
|[Testování částí kódu](/visualstudio/test/unit-test-your-code)|Popisuje, jak najít logické chyby v kódu pomocí testování částí.|
|[Testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní](/visualstudio/test/testing-sharepoint-2010-applications-with-coded-ui-tests)|Popisuje postup testování uživatelského rozhraní aplikací služby SharePoint.|

## <a name="see-also"></a>Viz také:

[Vytváření a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)
[zlepšení kvality kódu](/visualstudio/test/improve-code-quality)
