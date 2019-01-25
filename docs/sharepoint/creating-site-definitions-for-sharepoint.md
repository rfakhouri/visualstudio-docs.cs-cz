---
title: Vytváření definic webu pro službu SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, site definitions
- site definitions [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3b2709426cca892e60d864fa62695b2eef8c776b
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54874039"
---
# <a name="create-site-definitions-for-sharepoint"></a>Vytváření definic webu pro službu SharePoint
  Do projektu definice webu služby SharePoint [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] umožňuje vytvářet *definice webu*, který slouží jako základ pro nový web Sharepointu. Tyto definice nejen určit vzhled a chování webu služby SharePoint, ale jeho výchozí obsah a funkce. V definici můžete umístit předkonfigurované seznamy, typy obsahu, přijímače událostí, obrázky a další položky. SharePoint obsahuje několik definic webu například BLOGU, třeba. Při vytváření webu na základě definice webu BLOGU webu obsahuje seznamy, webové části a další položky, které vyžaduje blogovací web.  
  
 Další informace o definic webu najdete v tématu [šablony webu a definice](http://go.microsoft.com/fwlink/?LinkId=179134).  
  
## <a name="site-definition-projects"></a>Projekty definic webů
 Projekty definic v lokalitě [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] poskytují jenom základní soubory, které potřebuje webu služby SharePoint, se neposkytuje všechny funkce výchozí. Je nutné přidat soubory a obsah pro zajištění funkcí, které chcete. Webu můžete vytvořit ručně, vytváření a přidáním souborů, které potřebujete.  
  
## <a name="feature-stapling"></a>Připojování funkcí
 Jednou z výhod vytváření definic webu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] je, že budou automaticky používat *připojování funkcí*. Funkce sešívání připojí k definice webu namísto vložení jeho funkce v definici webu samotné funkce. Díky tomu můžete přidat funkci k žádné lokalitě vytvořené s použitím definice webu beze změny původní definice webu. Další informace najdete v tématu [připojování funkcí](http://go.microsoft.com/fwlink/?LinkID=119283).  
  
## <a name="site-definition-project-components"></a>Součásti projektu definice webu
 Při vytváření řešení definice webu následující výchozí soubory jsou přidány do jeho **SiteDefinition** uzlu.  
  
|Název souboru|Popis|  
|---------------|-----------------|  
|*default.aspx*|ASPX výchozí domovskou stránku pro nový web služby SharePoint.|  
|*onet.xml*|Určuje konfiguraci nového webu, součástí definice šablony webu a výchozí chování. Tato nastavení můžou patřit atributy jako typy obsahu, které jsou povolené, výchozí zobrazení seznamu souborů šablon dokumentů a webové části, které jsou součástí lokality. Ve výchozím nastavení `Modules` části jsou uvedené soubory, které chcete přidat do webu služby SharePoint a jak jsou sady nakonfigurované.|  
|*webtemp_\<SiteDefinitionName > .xml*|Určuje definici konfigurace lokality, které se zobrazí v **výběr šablony** část **novému Sharepointovému webu** stránky.|  
  
 Ve výchozím nastavení, všechny definice lokality jsou uloženy v  *\<jednotky: > \Program Files\Microsoft Shared\Web Server Extensions\14\TEMPLATE\SiteTemplates* složky. Každá definice lokality má své vlastní podsložce.  
  
## <a name="related-topics"></a>Související témata
  
|Název|Popis|  
|-----------|-----------------|  
|[Návod: Vytvoření základního projektu definice webu](../sharepoint/walkthrough-create-a-basic-site-definition-project.md)|Vás provede vytvořením základního projektu definice webu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|  
|[Postupy: Vytvoření vlastní stránky definice a konfigurace](http://go.microsoft.com/fwlink/?LinkId=183309)|Popisuje, jak vytvořit definici vlastního webu v Sharepointu zkopírováním existující definici lokality a následně tuto kopii upravit.|  
|[*WebTemp.xml*](http://go.microsoft.com/fwlink/?LinkId=183310)|Popisuje původní soubor, který určuje definic webu k dispozici v **výběr šablony** část **novému Sharepointovému webu** stránky.|  
|[Lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md)|Popisuje postup přípravy řešení služby SharePoint pro použití globální.|  
|[Vytvoření webové části pro SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)|Popisuje, jak můžete vytvořit části na stránku Sharepointu, který mohou uživatelé upravovat.|  
|[Vytvoření opakovaně použitelné ovládací prvky webové části nebo stránky aplikace](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|Popisuje, jak můžete vytvářet opakovaně použitelné ovládací prvky, které běží v stránkami aplikace a webové části.|  
|[Visual Web Developer](http://go.microsoft.com/fwlink/?LinkId=178725)|Popisuje způsob použití návrháře, který se zobrazí při otevření webové stránky ve vašem projektu.|  
|[Přehled webových stránek ASP.NET](http://go.microsoft.com/fwlink/?LinkId=178726)|Poskytuje obecné informace o struktuře [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] webové stránky, jak jsou zpracovány stránky [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)]a jak [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] stránky zobrazují kód, který splňuje standardy XHTML.|  
|[Syntaxe webové stránky ASP.NET](http://go.microsoft.com/fwlink/?LinkId=178727)|Popisuje elementy značek, které tvoří stránky ASP.NET.|  
|[Programování webových stránek ASP.NET](http://go.microsoft.com/fwlink/?LinkId=178728)|Poskytuje informace o tom, jak vytváření obslužných rutin událostí v [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] stránky a postupu při práci s klientským skriptem.|  
|[Programování ve službě Windows SharePoint Services](http://go.microsoft.com/fwlink/?LinkId=178729)|Popisuje způsob použití modelu spravovaného objektu, která je součástí [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)].|  
  
## <a name="see-also"></a>Viz také:
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
