---
title: Sloučení XML do funkce a balíku manifestů | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packaging
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e3697fe85d13e1131c58f28d572e443affa77a81
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875560"
---
# <a name="merge-xml-in-feature-and-package-manifests"></a>Sloučení XML do manifestů funkce a balíku
  Součásti a balíčky jsou definovány [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] soubory manifestu. Tyto zabalených manifestů jsou kombinací dat vygenerovaných z návrháře a vlastní [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] zadané v šabloně manifestu uživateli. Během vytváření balíčků [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] sloučí vlastní [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] příkazy s poskytnutou návrháře [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] k balení [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] soubor manifestu. Podobné prvky, s výjimkami uvedenými později v sloučit výjimky jsou sloučeny, aby [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] chyby ověření po nasazení souborů do služby SharePoint a chcete-li manifest soubory menší a efektivnější.  
  
## <a name="modify-the-manifests"></a>Upravit manifestů
 Zabalené soubory manifestu nemůžete upravovat přímo, dokud zakázat návrháři funkce nebo balíček. Však můžete ručně přidat vlastní [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] prvků, které se v šabloně manifestu prostřednictvím funkce a balíku návrháři nebo [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] editoru. Další informace najdete v tématu [jak: Přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md) a [jak: Přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
## <a name="feature-and-package-manifest-merge-process"></a>Funkce a balíku manifest proces sloučení
 Při kombinování vlastní elementy spolu s zadaný Návrhář prvky [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] používá následující proces. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kontroluje, zda každý prvek má jedinečnou hodnotu klíče. Pokud element nemá žádné jedinečnou hodnotu klíče, je připojen k souboru manifestu balíčku. Podobně nelze sloučit elementy, které mají více klíčů. Proto se připojují k souboru manifestu.  
  
 Pokud element má jedinečný klíč, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] porovnává hodnoty návrháře a vlastních klíčů. Pokud se hodnoty shodují, sloučí do jediné hodnoty. Pokud se hodnoty liší, návrháře hodnotu klíče jsou data zahozena a použít vlastní hodnotu klíče. Kolekce jsou také sloučeny. Například pokud generovaný návrhářem [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] a vlastní [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] současně obsahovat kolekci sestavení, manifest balíčku obsahuje pouze jednu kolekci sestavení.  
  
## <a name="merge-exceptions"></a>Sloučit výjimky
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Sloučí většina návrháře [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] prvky spolu s vlastní podobné [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] prvky, dokud mají jednu, jedinečné identifikační atribut. Nicméně některé prvky nemají jedinečný identifikátor, vyžaduje se pro [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] sloučení. Tyto prvky jsou označovány jako *sloučit výjimky*. V těchto případech [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nesloučí vlastní [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] prvky spolu s poskytnutou návrháře [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] elementů, ale místo toho je připojí k souboru manifestu balíčku.  
  
 Následuje seznam výjimek sloučení pro funkce a balíku [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] soubory manifestu.  
  
|Návrhář|– Element XML|  
|--------------|-----------------|  
|Funkce návrháře|ActivationDependency|  
|Funkce návrháře|UpgradeAction|  
|Návrháři balíčku|SafeControl|  
|Návrháři balíčku|CodeAccessSecurity|  
  
## <a name="feature-manifest-elements"></a>Elementy manifestu funkce
 V následující tabulce je seznam všech prvků manifestu funkce, které lze sloučit a jejich jedinečný klíč, který se použije pro porovnání.  
  
|Název elementu|Jedinečný klíč|  
|------------------|----------------|  
|Funkce (všechny atributy)|*Atribut název* (každý název atributu, elementu funkce, který je jedinečný klíč.)|  
|ElementFile|Umístění|  
|ElementManifests/ElementManifest|Umístění|  
|Vlastnost Properties /|Key|  
|CustomUpgradeAction|Název|  
|CustomUpgradeActionParameter|Název|  
  
> [!NOTE]  
>  Protože je jediný způsob, jak upravovat prvek CustomUpgradeAction ve vlastní [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] editoru nelze sloučit efekt je nízká.  
  
## <a name="package-manifest-elements"></a>Elementy manifestu balíčku
 V následující tabulce je seznam všech prvků manifestu balíčku, které lze sloučit a jejich jedinečný klíč, který se použije pro porovnání.  
  
|Název elementu|Jedinečný klíč|  
|------------------|----------------|  
|Řešení (všechny atributy)|*Atribut název* (každý atribut name elementu řešení je jedinečný klíč.)|  
|ApplicationResourceFiles/ApplicationResourceFile|Umístění|  
|Sestavení a sestavení|Umístění|  
|ClassResources/ClassResource|Umístění|  
|DwpFiles/DwpFile|Umístění|  
|FeatureManifests/FeatureManifest|Umístění|  
|/ Prostředků|Umístění|  
|RootFiles/RootFile|Umístění|  
|SiteDefinitionManifests/SiteDefinitionManifest|Umístění|  
|WebTempFile|Umístění|  
|TemplateFiles/TemplateFile|Umístění|  
|SolutionDependency|SolutionID|  
  
## <a name="manually-add-deployed-files"></a>Ručně přidejte nasazených souborů
 Některé elementy manifestu, například ApplicationResourceFile a DwpFiles, zadejte umístění, která obsahuje název souboru. Ale přidání záznam o názvu souboru manifestu šablony nepřidá základního souboru balíčku. Musíte přidat soubor do projektu, které chcete zahrnout do balíčku a odpovídajícím způsobem nastavte jeho vlastnost typ nasazení.  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
