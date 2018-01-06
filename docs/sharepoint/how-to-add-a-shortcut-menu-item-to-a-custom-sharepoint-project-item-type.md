---
title: "Postupy: Přidání položky místní nabídky do typu položky projektu služby SharePoint vlastní | Microsoft Docs"
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
ms.assetid: f6ec47a7-e7d9-4e26-810b-77943a1ab04c
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6875b03c86580328f2e29f701b77c07d646ffca1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type"></a>Postupy: Přidání položky místní nabídky do vlastního typu položky projektu služby SharePoint
  Když definujete vlastní typu položky projektu služby SharePoint, můžete přidat položky místní nabídky do položky projektu. Položky nabídky se zobrazí, když uživatel klikne pravým tlačítkem myši na položku projektu v **Průzkumníku řešení**.  
  
 Následující postup předpokládá, že jste již definovali vlastního typu položky projektu služby SharePoint. Další informace najdete v tématu [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
### <a name="to-add-a-shortcut-menu-item-to-a-custom-project-item-type"></a>Přidání položky místní nabídky do vlastního typu položky projektu  
  
1.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> události *projectItemTypeDefinition* parametr.  
  
2.  Ve vaší obslužné rutiny události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> událostí, přidejte nový <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> do objektu <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> nebo <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> kolekce parametru argumentů události.  
  
3.  V <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> obslužné rutiny události pro nové <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu, provádět úlohy, kterou chcete spustit, když uživatel vybere vaší položky místní nabídky.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat položky kontextové nabídky vlastního typu položky projektu. Když uživatel otevře z položky projektu v místní nabídce **Průzkumníku řešení** a vybere **zapsat zprávu do okna výstupu** položky nabídky, Visual Studio zobrazí zprávu v **výstup**  okno.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypemenu.cs#4)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypemenu.vb#4)]  
  
 Tento příklad používá zapsat zprávu do projektu služby SharePoint **výstup** okno. Další informace najdete v tématu [pomocí projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje projektu knihovny tříd s odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>Položka projektu nasazení  
 Pokud chcete povolit jiné vývojářům používat vaše položky projektu, vytvořte šablona projektu nebo šablony položek projektu. Další informace najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Chcete-li nasadit položku projektu, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení, šablony a další soubory, které chcete distribuovat do položky projektu. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: definování typu položky projektu služby SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Postupy: Přidání vlastnosti do typu položky projektu služby SharePoint vlastní](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  