---
title: "Aspekty řešení v izolovaném prostoru | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.SandboxedSolutions
- VS.SharePointTools.Security.SandboxedSolutions
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, sandboxed solutions
- sandboxed solutions [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, farm solutions
- farm solutions [SharePoint development in Visual Studio]
ms.assetid: 6c2d2dc6-4acb-4b68-ba94-a61087e8dff0
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4598b100572bb47fd537e8edad927d78b4f1550
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sandboxed-solution-considerations"></a>Aspekty řešení v izolovaném prostoru
  *Řešení v izolovaném prostoru* jsou funkcí v produktu Microsoft SharePoint 2010, která umožní uživatelům kolekce lokality nahrát vlastní řešení vlastní kód. Běžné řešení v izolovaném prostoru je uživatelé nahrání vlastní webové části.  
  
 V izolovaném prostoru aplikace SharePoint běží v zabezpečené, monitorovaného procesu, který má přístup k omezené součástí webové farmy. Microsoft SharePoint 2010 používá kombinaci funkcí, galerie řešení, řešení pro monitorování a ověření rozhraní povolit řešení v izolovaném prostoru.  
  
## <a name="specifying-project-trust-level"></a>Určení úrovně důvěryhodnosti projektu  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]podporuje řešení v izolovaném prostoru prostřednictvím vlastnosti projektu logická hodnota volána *řešení v izolovaném prostoru*. Tuto vlastnost lze nastavit na libovolný čas v projektu, nebo můžete zadat, když vytvoříte projekt v **Průvodce vlastním nastavením SharePoint**.  
  
> [!NOTE]  
>  Změna *řešení v izolovaném prostoru* vlastnosti projektu po vytvoření může dojít k chybám ověření.  
  
 Řešení je považován za řešení farmy obor, pokud *řešení v izolovaném prostoru* je nastavena na **false** nebo zvolíte **nasadit jako řešení farmy** možnost. Však řešení je zpracovávat odděleně od řešení farmy Pokud *řešení v izolovaném prostoru* je nastavena na **true** nebo zvolíte **nasadit jako řešení v izolovaném prostoru** možnost v průvodci.  
  
## <a name="sharepoint-site-hierarchy"></a>Hierarchie webu služby SharePoint  
 Zjistit, jak v izolovaném prostoru řešení práce, pomáhá vědět, jestli jsou weby služby SharePoint hierarchické v oboru. Element nejvyšší se označuje jako webové farmy a další elementy jsou k němu podřízené:  
  
 Webové farmy  
  
 Webové aplikace A  
  
 A1 kolekce lokality  
  
 A1a lokality  
  
 Webovou aplikaci B  
  
 Kolekce B1 lokality  
  
 B1a lokality  
  
 B1b lokality  
  
 Kolekce B2 lokality  
  
 B2a lokality  
  
 Jak vidíte, webové farmy může obsahovat jeden nebo více webových aplikací, které pak mohou obsahovat jeden nebo více kolekcích webů, které může mít podřízené lokality a tak dále. Změny provedené jednu kolekci vliv lokality, pouze to, že kolekce webů a žádné jiné. Změny provedené na úrovni webové farmy však vliv na všechny kolekce webů na farmě.  
  
 Windows SharePoint Services (WSS) 3.0 umožňuje nasadit řešení jenom na úrovni farmy, ale [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] umožňuje nasadit na úrovni farmy (řešení farmy) nebo úrovni kolekce webů (řešení v izolovaném prostoru).  
  
## <a name="why-sandboxed-solutions"></a>Proč řešení v izolovaném prostoru?  
 V WSS 3.0 řešení může být nasazený jenom na úrovni farmy. Vynutila si, že potenciálně škodlivého nebo destabilizing řešení může být nasazený ovlivňující celou webové farmy a všechny ostatní kolekce webů a aplikací, které běží v něm. Pomocí řešení v izolovaném prostoru však můžete nasadit řešení na podoblasti farmy, určité kolekci webů. Zajistit další ochranu na řešení sestavení není načtena do hlavní [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] proces (w3wp.exe). Místo toho je načten do samostatného procesu (SPUCWorkerProcess.exe). Tento proces je monitorována a implementuje kvóty a omezení pro ochranu farmy z řešení v izolovaném prostoru, které provádějí škodlivých aktivit, jako je například spuštění úzkou cykly, které využívají cyklů procesoru.  
  
## <a name="site-collection-solution-gallery"></a>Galerie řešení kolekce webů  
 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)]2010 obsahuje funkce, která se označuje jako "galerii kolekce webů řešení." Tuto funkci můžete přistupovat na stránce Centrální správa SharePoint 2010 nebo otevřením **Akce webu** nabídce Výběr **nastavení lokality**a pak vyberete **řešení** v části **galerií** na webu služby SharePoint. Galerie řešení jsou úložiště řešení, které umožňují správci kolekce webů ke správě řešení v jejich kolekce webů.  
  
 Galerie řešení je knihovna dokumentů uložená v kořenovém webovou stránku služby SharePoint. Galerie řešení nahrazuje šablony webů a podporuje balíčků řešení. Při odeslání souboru balíčku (WSP) řešení služby SharePoint, je zpracován jako řešení v izolovaném prostoru.  
  
## <a name="sandboxed-solution-limitations"></a>Omezení řešení v izolovaném prostoru  
 Po nasazení řešení v izolovaném prostoru pole funkce služby SharePoint je k dispozici k němu je omezený na snížit žádné chyby zabezpečení, které může mít. Některé z těchto omezení zahrnují následující:  
  
-   Řešení v izolovaném prostoru mít omezená podmnožina elementů nasadit řešení, která je jim dostupná. Potenciálně citlivé šablon projektu služby SharePoint, například lokality definice a pracovní postupy, nejsou k dispozici.  
  
-   SharePoint běží řešení v izolovaném prostoru kódu v procesu (SPUCWorkerProcess.exe) oddělený od hlavní [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] proces fondu (w3wp.exe) aplikace.  
  
-   Mapované složky nelze přidat do projektu.  
  
-   Typy, které do [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] sestavení Microsoft.Office.Server nelze použít v řešení v izolovaném prostoru. Navíc pouze typy, které do [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] sestavení Microsoft.SharePoint lze použít v řešení v izolovaném prostoru.  
  
 Je důležité si uvědomit, že zadání řešení služby SharePoint jako řešení v izolovaném prostoru nemá žádný vliv na server služby SharePoint. pouze určuje, jak nasazení projektu služby SharePoint do služby SharePoint z [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a jaké sestavení, která se váže k. Soubor generovaný WSP nemá vliv, a WSP soubor neobsahuje žádná data, která přímo koreluje s *řešení v izolovaném prostoru* vlastnost.  
  
## <a name="capabilities-and-elements-in-sandboxed-solutions"></a>Možnosti a elementů v řešení v izolovaném prostoru  
 Řešení v izolovaném prostoru podporují následující možnosti a prvky:  
  
-   Typy nebo pole obsahu  
  
-   Vlastní akce  
  
-   Deklarativní pracovní postupy  
  
-   Přijímače událostí  
  
-   Funkce popisky  
  
-   Definice seznamů  
  
-   Instance seznamů  
  
-   Soubory modulu nebo  
  
-   Navigace  
  
-   Onet.XML  
  
-   SPItemEventReceiver  
  
-   SPListEventReceiver  
  
-   SPWebEventReceiver  
  
-   Podpora pro všechny webové části, které jsou odvozeny od`System.Web.UI.WebControls.WebParts.WebPart`  
  
-   Webové části  
  
-   Prvky funkce WebTemplate (namísto Webtemp.xml)  
  
-   Visual webové části  
  
 Řešení v izolovaném prostoru nepodporují následující možnosti a prvky:  
  
-   Stránky aplikací  
  
-   Vlastní akce skupiny  
  
-   Součásti pro celou farmu  
  
-   `HideCustomAction` – element  
  
-   Web s rozsahem aplikace – funkce  
  
-   Pracovní postupy pomocí kódu  
  
## <a name="see-also"></a>Viz také  
 [Rozdíly mezi řešeními v izolovaném prostoru a ve farmách](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  