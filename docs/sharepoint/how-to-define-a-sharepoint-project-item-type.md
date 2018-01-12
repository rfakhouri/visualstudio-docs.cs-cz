---
title: "Postupy: definování typu položky projektu služby SharePoint | Microsoft Docs"
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
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 24ead19b6e79b2f6003847483877cdcaf3440890
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-define-a-sharepoint-project-item-type"></a>Postupy: Definování typu položky projektu SharePoint
  Pokud chcete vytvořit vlastní položky projektu služby SharePoint, definování typu položky projektu. Další informace najdete v tématu [definování vlastní SharePoint typů položek projektu](../sharepoint/defining-custom-sharepoint-project-item-types.md).  
  
### <a name="to-define-a-project-item-type"></a>K definování typu položky projektu  
  
1.  Vytvoření projektu knihovny tříd.  
  
2.  Přidejte odkazy na následující sestavení:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní.  
  
4.  Přidejte do třídy následující atributy:  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> typ do konstruktoru atributu.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. V definici typu položky projektu tento atribut určuje identifikátor řetězce pro nové položky projektu. Doporučujeme použít formát *název společnosti*. *název funkce* abyste měli jistotu, že všechny položky projektu mít jedinečný název.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute>. Tento atribut určuje ikonu k zobrazení této položky projektu v **Průzkumníku řešení**. Tento atribut je volitelná. Pokud jste se nevztahují na třídě, Visual Studio zobrazí výchozí ikonu pro tuto položku projekt. Pokud nastavíte tento atribut, předejte plně kvalifikovaný název ikony nebo rastrový obrázek, který je vložen do vašeho sestavení.  
  
5.  V implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metoda, použijte členy *projectItemTypeDefinition* parametr pro definování chování typu položky projektu. Tento parametr je <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> objekt, který poskytuje přístup k událostí definovaných v <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> rozhraní. Pro přístup ke konkrétní instanci typu položky projektu, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> událostech, například <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak k definování typu položky projektu jednoduché. Tento typ položky projektu zapíše zprávu, která **výstup** okno a **seznam chyb** okno při přidání položky projektu tohoto typu do projektu.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemtype.vb#2)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#2](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemtype.cs#2)]  
  
 Tento příklad používá zapsat zprávu do projektu služby SharePoint **výstup** okno a **seznam chyb** okno. Další informace najdete v tématu [pomocí projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>Položka projektu nasazení  
 Pokud chcete povolit jiné vývojářům používat vaše položky projektu, vytvořte šablona projektu nebo šablony položek projektu. Další informace najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Chcete-li nasadit položku projektu, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení, šablony a další soubory, které chcete distribuovat do položky projektu. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Vytváření šablon položek a projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Postupy: Přidání vlastnosti do typu položky projektu služby SharePoint vlastní](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Postupy: Přidání položky místní nabídky do vlastního typu položky projektu služby SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)  
  
  