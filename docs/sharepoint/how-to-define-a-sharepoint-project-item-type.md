---
title: 'Postupy: Definování typu položky projektu služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bfb04256a1bb8aacb062f30839566b75b599a3a3
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54872024"
---
# <a name="how-to-define-a-sharepoint-project-item-type"></a>Postupy: Definování typu položky projektu SharePoint
  Definování typu položky projektu, pokud chcete vytvořit vlastní položky projektu služby SharePoint. Další informace najdete v tématu [definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md).  
  
### <a name="to-define-a-project-item-type"></a>K definování typu položky projektu  
  
1.  Vytvořte projekt knihovny tříd.  
  
2.  Přidejte odkazy na následující sestavení:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní.  
  
4.  Přidejte do třídy následující atributy:  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> typ konstruktoru atributu.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. V definici typu položky projektu tento atribut určuje identifikátor řetězce pro novou položku projektu. Doporučujeme použít formát *název společnosti*. *název funkce* abyste měli jistotu, že všechny položky projektu mít jedinečný název.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute>. Tento atribut určuje ikonu k zobrazení pro tuto položku projektu v **Průzkumníka řešení**. Tento atribut je volitelná. Pokud jste se nevztahují na vaší třídy, Visual Studio zobrazí výchozí ikonu pro položky projektu. Pokud je tento atribut nastaven, předejte plně kvalifikovaný název ikona nebo rastrový obrázek, který je vložen do vašeho sestavení.  
  
5.  Ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metody, použijte členy *projectItemTypeDefinition* parametr definuje chování typu položky projektu. Tento parametr je <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> objekt, který poskytuje přístup k události definované v <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> rozhraní. Přístup ke konkrétní instanci typu položky projektu, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> událostech, například <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak definovat typ položky simple projektu. Zapíše zprávu do tohoto typu položky projektu **výstup** okno a **seznam chyb** okno, když uživatel přidá tohoto typu položky projektu do projektu.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemtype.vb#2)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemtype.cs#2)]  
  
 Tento příklad používá k zápisu zprávy do projektu služby SharePoint **výstup** okno a **seznam chyb** okna. Další informace najdete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje odkazy na následující sestavení:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-project-item"></a>Nasazení položky projektu  
 Povolit ostatním vývojářům použít vaši položku projektu, vytvořte šablonu projektu nebo šablony položky projektu. Další informace najdete v tématu [položky vytvářet šablony a šablony projektů pro položky Sharepointového projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 K nasazení položky projektu, vytvořit [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení, šablony a další soubory, které chcete distribuovat do položky projektu. Další informace najdete v tématu [nástroje nasazení rozšíření pro SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také:
 [Definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Vytváření šablon položek a projektů pro položky projektu SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Postupy: Přidání položky místní nabídky do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)  
