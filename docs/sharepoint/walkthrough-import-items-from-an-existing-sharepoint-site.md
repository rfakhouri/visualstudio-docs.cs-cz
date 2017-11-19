---
title: "Návod: Import položek z existující stránky SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
ms.assetid: faac3309-88d7-4fb2-8392-feda07fc00e5
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 602615426a8aeca118f6faba65e21778136b0ce6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-import-items-from-an-existing-sharepoint-site"></a>Návod: Import položek z existující stránky SharePoint
  Tento návod ukazuje, jak import položek z existující stránky SharePoint do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Přizpůsobení webu služby SharePoint můžete přidat sloupec vlastní lokality (také označované jako *pole*.  
  
-   Export do souboru WSP webu služby SharePoint.  
  
-   Import souborů WSP do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] služby SharePoint pomocí WSP Importovat projekt.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="customizing-a-sharepoint-site"></a>Přizpůsobení webu služby SharePoint  
 V tomto příkladu vytvoříte a přizpůsobit podřízeného webu služby SharePoint a přidání nového sloupce webu do jiného podřízeného webu pro pozdější použití. Později budete exportovat do souboru WSP první web a pak importovat sloupec vlastní lokality do druhé podřízeného webu pomocí WSP Importovat projekt.  
  
#### <a name="to-create-and-customize-a-sharepoint-site"></a>Vytvářet a přizpůsobovat webu služby SharePoint  
  
1.  Otevřete web služby SharePoint pomocí webového prohlížeče, jako je například http://*systémový název*/SitePages/Home.aspx.  
  
2.  Vytvořit podřízenou lokalitu z hlavní web služby SharePoint tak, že otevřete **Akce webu** nabídky a pak vyberete **nové lokality**.  
  
3.  Na webu **vytvořit** dialogovém okně vyberte **prázdný web** typu.  
  
4.  V **název** zadejte **lokality sloupec Test 1**; v **název adresy URL** zadejte **columntest1**; nechte ostatní nastavení na výchozí hodnoty; a potom zvolte **vytvořit** tlačítko.  
  
5.  Po vytvoření webu, přejděte v prohlížeči zpět na web hlavní http://*systémový název*/SitePages/Home.aspx.  
  
6.  Znovu vytvořit prázdnou podřízenou lokalitu z hlavní web služby SharePoint otevřením **Akce webu** nabídce Výběr **nové lokality**a pak vyberete **prázdný web** typu.  
  
7.  V **název** zadejte **lokality sloupec Test 2**; v **název adresy URL** zadejte **columntest2**; nechte ostatní nastavení na výchozí hodnoty; a potom zvolte **vytvořit** tlačítko.  
  
8.  Přejděte zpět na první web http://*SystemName*/columntest1/default.aspx.  
  
9. Na **Akce webu** nabídce zvolte **nastavení lokality** zobrazíte na stránce Nastavení webu.  
  
10. V **galerií** zvolte **sloupce webu** odkaz.  
  
11. V horní části **Galerie sloupců webu** vyberte **vytvořit** tlačítko.  
  
12. V **název sloupce** zadejte **testovací sloupec**, ponechte výchozí hodnoty a potom zvolte **OK** tlačítko.  
  
13. **Testovací sloupec** sloupec se zobrazí ve sloupci vlastní nadpis v galerii sloupce webu.  
  
## <a name="exporting-the-sharepoint-site"></a>Export Web služby SharePoint  
 V dalším kroku získat soubor SharePoint instalační program (WSP), který obsahuje položky služby SharePoint a elementy, které chcete importovat do vaší [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint. Pokud již soubor WSP nemáte, musíte z existující stránky SharePoint vytvořit. V tomto příkladu budete exportovat do souboru WSP výchozí web služby SharePoint.  
  
> [!IMPORTANT]  
>  Pokud se zobrazí chyba v běhu provedením tohoto postupu, budete muset proveďte postup v systému, který má přístup k webu služby SharePoint.  
  
#### <a name="to-export-an-existing-sharepoint-site"></a>Chcete-li exportovat existující stránky SharePoint  
  
1.  Na webu služby SharePoint, zvolte **nastavení lokality** na **Akce webu** zobrazíte na stránce Nastavení webu.  
  
2.  V **Akce webu** část stránky Nastavení lokality, vyberte **web uložit jako šablonu** odkaz.  
  
3.  V **název souboru** zadejte **ExampleSite**a v **název šablony** zadejte **lokality příklad**.  
  
4.  V tomto příkladu ponechte **zahrnout obsah** zaškrtnutí políčka zrušte.  
  
     Pokud vyberete toto políčko, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uloží do souboru WSP všechny seznamy a knihovny dokumentů a jejich obsah. I když to je užitečné v některých případech, není nutné v tomto příkladu.  
  
5.  Po úspěšném dokončení operace, vyberte **řešení Galerie** odkaz k zobrazení souboru WSP.  
  
     Pro zobrazení stránky galerie řešení novější, otevřete **Akce webu** nabídce zvolte **nastavení lokality**, zvolte **přejít na nastavení lokality nejvyšší úrovně** odkaz v  **Správa kolekce lokalit** části a potom vyberte **řešení** na odkaz v **galerií** části.  
  
6.  V Galerii řešení, vyberte **ExampleSite** odkaz.  
  
7.  V **stažení souboru** dialogovém okně vyberte **Uložit** tlačítko pro uložení souboru v lokálním systému, ve výchozím nastavení v složky se staženými soubory.  
  
## <a name="importing-the-wsp-file"></a>Import souborů WSP  
 Teď, když máte WSP soubor, který obsahuje položky, kterou chcete znovu použít (vlastní stránky sloupec testovací sloupec), import souborů WSP k přístupu.  
  
#### <a name="to-import-a-wsp-file"></a>Import souborů WSP  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], na řádku nabídek zvolte **soubor**, **nový**, **projektu** zobrazíte **nový projekt** dialogové okno. Pokud vaše IDE nastaven pro použití nastavení vývoj jazyka Visual Basic, v řádku nabídek, zvolte **soubor**, **nový projekt**.  
  
2.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
3.  Vyberte **importu služby SharePoint 2010 řešení balíček** šablony v **šablony** podokně, ponechejte pole název projektu jako WspImportProject1 a potom vyberte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
4.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] pro druhý podřízeného webu služby SharePoint, kterou jste vytvořili dříve. Budete přidávat nová vlastní pole položek, http://*systémový název*/columntest2 do tohoto podřízeného webu.  
  
5.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** část, ponechte výběr jako **nasadit jako řešení v izolovaném prostoru**.  
  
6.  V **zadejte nový zdroj projektu** stránce, přejděte do umístění na serveru, kam jste uložili soubor WSP, dříve a pak vyberte **Další** tlačítko.  
  
    > [!NOTE]  
    >  Pokud se rozhodnete **Dokončit** tlačítko na této stránce, všechny dostupné položky v souboru WSP budou importovány.  
  
7.  V **vybrat položky k importu** pole, zrušte zaškrtnutí všech políček v seznamu, s výjimkou **testovací sloupec**a potom zvolte **Dokončit** tlačítko.  
  
     Vzhledem k tomu, že seznam obsahuje mnoho položek, můžete zvolit Ctrl + klíče vyberte všechny položky v seznamu, vyberte klíč MEZERNÍK zrušte zaškrtnutí všech políček a potom vyberte zaškrtněte políčko vedle položky **testovací sloupec** položky.  
  
     Po dokončení operace importu nový projekt s názvem **WspImportProject1** se vytvoří složku s názvem, který obsahuje **pole**. V této složce se sloupci vlastní stránky **testovací sloupec** a jeho definice souboru Elements.xml.  
  
## <a name="deploying-the-project"></a>Nasazení projektu  
 Nakonec nasazení **WspImportProject1** na druhý server SharePoint podřízeného webu, že jste dříve vytvořili zobrazení sloupci vlastní stránky.  
  
#### <a name="to-deploy-the-project"></a>K nasazení projektu  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vyberte nasazení a spuštění projektu import WSP klávesy F5.  
  
2.  Na webu služby SharePoint otevřete **Akce webu** nabídce a potom zvolte **nastavení lokality** zobrazíte na stránce Nastavení webu.  
  
3.  V **galerií** zvolte **sloupce webu** odkaz.  
  
4.  Přejděte dolů k položce **vlastní sloupce** části.  
  
     Všimněte si, že sloupec vlastní lokality, který jste importovali z první web služby SharePoint se zobrazí v seznamu.  
  
## <a name="see-also"></a>Viz také  
 [Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  