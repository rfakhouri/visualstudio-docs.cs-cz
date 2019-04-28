---
title: Profilace výkonu aplikací služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8b59a3de88403300a46b7992a2dad72e3d6b59e0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62563309"
---
# <a name="profile-the-performance-of-sharepoint-applications"></a>Profil výkonu aplikací služby SharePoint

Pokud vaše aplikace SharePoint fungují pomalu nebo neefektivně, můžete použít funkce profilování v sadě Visual Studio k určení problematického kódu a další prvky. Pomocí funkce testování zatížení, můžete určit, jakým způsobem aplikace SharePoint funguje pod zátěží, například když mnoho uživatelů současně k aplikaci. Spuštěním testů webového výkonu lze změřit, jak aplikace funguje na webu. Pomocí programových testů UI můžete ověřit, zda celá aplikaci SharePoint, včetně uživatelského rozhraní, funguje správně. Použijete-li tyto testy společně, mohou pomoci identifikovat problémy s výkonem před nasazením aplikace.

## <a name="profile-tools-overview"></a>Přehled nástroje profilu

Profilování se vztahuje k procesu sledování a zaznamenávání chování výkonu aplikace při jejím spuštění. Pomocí Profilování vaší aplikace můžete odhalit problémy, jako jsou problémová místa, neefektivní kód a problémy s přidělením paměti, které způsobují aplikace pracuje pomalu nebo používá příliš mnoho paměti. Například můžete profilování k identifikaci aktivních bodů ve vašem kódu, které jsou segmenty kódů, které jsou často volány a mohou zpomalit výkon vaší aplikace. Po identifikaci aktivních oblastí, můžete často optimalizovat nebo odstranit.

Několik nástrojů pro profilaci v integrovaném vývojovém prostředí (IDE) můžete použít k identifikaci a vyhledání tyto typů problémů s výkonem. Tyto nástroje pracují stejným způsobem pro projekty služby SharePoint, jako je tomu u jiných typů projektů sady Visual Studio. Průvodce Profilováním výkonu nástroje vás provede vytvořením relace výkonu, která používá testy, které zadáte. Relace výkonu je sada konfiguračních dat, která se používá ke shromažďování informací o výkonu z aplikace spolu s výsledky jednoho nebo několika spuštění profilování. Výkonnostní relace jsou uloženy ve složce vašeho projektu a můžete zobrazit v **prohlížeč výkonu**. Další informace najdete v tématu [metody kolekce výkonu Principy](../profiling/understanding-performance-collection-methods.md).

Po vytvoření a spuštění analýzy profilu v aplikaci sestava obsahuje podrobné informace o jeho výkonu. Tato sestava může obsahovat položky jako graf využití procesoru v čase, zásobník volání hierarchické funkce nebo volání stromu. Přesný obsah zprávy se může lišit v závislosti na typu testu, který spouštíte, jako je například vzorkování nebo instrumentace. Další informace najdete v tématu [přehled nástrojů profilování sestavy](http://go.microsoft.com/fwlink/?LinkId=224689).

## <a name="performance-session-process"></a>Proces relace výkonu

Chcete-li Profilovat aplikaci, začněte pomocí Průvodce Profilováním výkonu nástroje pro tvorbu relace výkonu. V panelu nabídky zvolte **analyzovat**, **spustit Průvodce výkonem**. Po dokončení průvodce, zadejte požadované informace pro vaši relaci výkonu, jako je například požadovanou metodu profilu a aplikaci, kterou chcete Profilovat. Další informace najdete v tématu [jak: Profilovat webové stránky nebo webové aplikace pomocí průvodcem výkonu](http://go.microsoft.com/fwlink/?LinkId=224692). Jako alternativu můžete použít možnosti příkazového řádku k nastavení a spuštění relace výkonu. Další informace najdete v tématu [Profiling Tools z příkazového řádku pomocí](http://go.microsoft.com/fwlink/?LinkId=224703). Pokud chcete ručně konfigurovat každý aspekt relace výkonu, přečtěte si téma [jak: Ruční vytváření výkonnostních relací s nástroji pro profilaci](http://go.microsoft.com/fwlink/?LinkId=224691). Můžete také vytvořit relaci výkonu z testu jednotky, v **výsledky testu** okno, otevřením místní nabídky pro test jednotek a následným výběrem možnosti **vytvořit relaci výkonu**.

Po nastavení relace výkonu, konfigurace relace uložena, server je nakonfigurován pro poskytnutí profilování dat a spuštění aplikace. Při použití aplikace, data výkonu jsou zapsána do souboru protokolu. Výkonnostní relace jsou uvedeny v **prohlížeč výkonu** pod **cíle** složky. Po ukončení relace výkonu se jeho sestava zobrazí ve **sestavy** složky **prohlížeč výkonu**. Pokud chcete zobrazit sestavy, otevřete ho v **prohlížeč výkonu**. Chcete-li zobrazit nebo nakonfigurovat vlastnosti relace výkonu, otevřete místní nabídku v **prohlížeč výkonu**a klikněte na tlačítko **vlastnosti**. Další informace o konkrétních vlastnostech relace výkonu naleznete v tématu [konfigurace výkonnostních relací pro nástroje pro profilaci sady](http://go.microsoft.com/fwlink/?LinkId=224694). Informace o interpretaci výsledků výkonu relace naleznete v tématu [analýza dat nástrojů pro profilaci](http://go.microsoft.com/fwlink/?LinkId=224704).

## <a name="stress-test"></a>Zátěžový test

Výkon napětí aplikací můžete analyzovat vytvořením zátěžových testů a testů výkonnosti webu v sadě Visual Studio. Když vytvoříte zátěžový test v sadě Visual Studio, určete kombinace faktorů, nazývá scénář, chcete-li aplikaci otestovat. Tyto faktory zahrnují vzor zatížení, model kombinace testů, kombinaci testů, kombinaci sítí a kombinaci webového prohlížeče. Scénáře testování zatížení můžete zahrnout jednotkové testy i testy výkonnosti webu.

Obrázek 1: Příklad výsledků zátěžového testování

![Spuštění zátěžového testu zobrazení grafů](../sharepoint/media/load-webgraphs.png "běžícímu zátěžovému testu zobrazení grafů")

Testy výkonu webu simulují, jak koncový uživatel může interaktivně pracovat s aplikací SharePoint. Můžete vytvořit testy webového výkonu zaznamenáním požadavků HTTP v relaci prohlížeče nebo pomocí **rekordéru testů výkonnosti webu**. Webové požadavky zobrazují v **editoru testu výkonnosti webu** po ukončení relace prohlížeče. Potom můžete ladit výsledky v **prohlížeče výsledků testu výkonnosti webu**. Testy výkonnosti webu můžete vytvořit také ručně pomocí **editoru testu výkonnosti webu**.

## <a name="test-user-interfaces"></a>Testování uživatelského rozhraní

Programové testy UI bude automaticky řídit aplikaci SharePoint prostřednictvím jeho uživatelské rozhraní (UI). Tyto testy zahrnují ovládací prvky uživatelského rozhraní, jako jsou tlačítka a nabídky, chcete-li ověřit, že správně fungují. Tento druh testování je zvláště užitečný, pokud ověření nebo jiná logika se provádí v uživatelském rozhraní, například na webové stránce. Programové testy uživatelského rozhraní můžete také použít k automatizaci ručních testů. Můžete vytvořit kódované testy uživatelského rozhraní aplikací služby SharePoint stejně jako při vytváření testů pro ostatní typy aplikací. Další informace najdete v tématu [testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní](../test/testing-sharepoint-2010-applications-with-coded-ui-tests.md).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Návod: Profil aplikace služby SharePoint](../sharepoint/walkthrough-profiling-a-sharepoint-application.md)|Ukazuje, jak provést analýzu profilu odběru vzorků v aplikaci SharePoint.|
|[Testování výkonu aplikace před vydáním](/azure/devops/test/load-test/run-performance-tests-app-before-release?view=vsts)|Popisuje, jak vytvořit testy zatížení, které vám pomohou testovat zátěže aplikace SharePoint.|
|[Testování částí kódu](../test/unit-test-your-code.md)|Popisuje, jak najít logické chyby v kódu pomocí testování částí.|
|[Testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní](../test/testing-sharepoint-2010-applications-with-coded-ui-tests.md)|Tento článek popisuje testování uživatelského rozhraní aplikací služby SharePoint.|

## <a name="see-also"></a>Viz také:

- [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)
- [Zlepšení kvality kódu](../test/improve-code-quality.md)