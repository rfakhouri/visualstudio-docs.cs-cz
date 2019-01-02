---
title: 'Postupy: Přidání položky místní nabídky do projektů služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ba38984b5c49dbf834286414e61734fe46069876
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964134"
---
# <a name="how-to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>Postupy: Přidání položky místní nabídky do projektů služby SharePoint
  Můžete přidat položky místní nabídky do jakéhokoli projektu SharePoint. Položka nabídky se zobrazí, když uživatel klepne pravým tlačítkem myši na uzel projektu v **Průzkumníka řešení**.  
  
 Následující postup předpokládá, že jste již vytvořili projekt rozšíření. Další informace najdete v tématu [jak: Vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
### <a name="to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>Přidání položky místní nabídky do projektů služby SharePoint  
  
1.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> událost *projectService* parametru.  
  
2.  V obslužné rutině události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> události, přidejte novou <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.ActionMenuItems%2A> nebo <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.AddMenuItems%2A> kolekce parametr argumenty události.  
  
3.  V <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> obslužné rutiny události pro nové <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu, provádět úlohy, kterou chcete spustit, když uživatel klikne vaší položky místní nabídky.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje přidání položky místní nabídky do projektů uzlů SharePoint v **Průzkumníka řešení**. Když uživatel klepne pravým tlačítkem myši uzel projektu a klikne **zapsat zprávu do okna výstup** položku nabídky, Visual Studio zobrazí zprávu v **výstup** okna. Tento příklad používá projektu služby SharePoint k zobrazení zprávy. Další informace najdete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
 [!code-csharp[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/CSharp/projectmenu/extension/projectitemextensionmenu.cs#1)]
 [!code-vb[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/VisualBasic/projectmenu/extension/projectitemextensionmenu.vb#1)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje projekt knihovny tříd s odkazy na následující sestavení:  
  
-   Microsoft.VisualStudio.SharePoint
-     
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md)   
 [Postupy: Vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [Postupy: Přidání vlastnosti do projektů služby SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)  
