---
title: "Postupy: Přidání položky místní nabídky do rozšíření položky projektu služby SharePoint | Microsoft Docs"
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
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
ms.assetid: d00513a6-d66d-4fbe-9efa-ef3b08c9a73a
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7c3cb29fa90917f50b42579bf6f274aa8a20d99f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension"></a>Postupy: Přidání položky místní nabídky do rozšíření položky projektu služby SharePoint
  Položky místní nabídky můžete přidat do existující položky projektu služby SharePoint pomocí rozšíření položky projektu. Položky nabídky se zobrazí, když uživatel klikne pravým tlačítkem myši na položku projektu v **Průzkumníku řešení**.  
  
 Následující postup předpokládá, že jste již vytvořili rozšíření položky projektu. Další informace najdete v tématu [postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
### <a name="to-add-a-shortcut-menu-item-in-a-project-item-extension"></a>Přidat položky místní nabídky do rozšíření položky projektu  
  
1.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> události *projectItemType* parametr.  
  
2.  Ve vaší obslužné rutiny události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> událostí, přidejte nový <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> do objektu <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> nebo <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> kolekce parametru argumentů události.  
  
3.  V <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> obslužné rutiny události pro nové <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu, provádět úlohy, kterou chcete spustit, když uživatel klikne vaší položky místní nabídky.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat položky místní nabídky do položky projektu přijímač událostí. Při kliknutí pravým tlačítkem na položku projektu v **Průzkumníku řešení** a klikne na tlačítko **zapsat zprávu do okna výstupu** položky nabídky, Visual Studio zobrazí zprávu v **výstup**okno.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionmenu.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionmenu.cs#1)]  
  
 Tento příklad používá zapsat zprávu do projektu služby SharePoint **výstup** okno. Další informace najdete v tématu [pomocí projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje projektu knihovny tříd s odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Postupy: Přidání vlastnosti do rozšíření položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)   
 [Návod: Rozšiřování typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  