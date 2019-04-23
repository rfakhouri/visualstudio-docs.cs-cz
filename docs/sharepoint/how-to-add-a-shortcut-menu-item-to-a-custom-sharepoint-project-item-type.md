---
title: 'Postupy: Přidání položky místní nabídky do typu položky projektu SharePoint vlastní | Dokumentace Microsoftu'
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
ms.openlocfilehash: 7de1bf04137c0e799e19e658307d630ec3fa6a78
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068740"
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type"></a>Postupy: Přidání položky místní nabídky do vlastního typu položky projektu SharePoint
  Při definování vlastního typu položky projektu služby SharePoint, můžete přidat položky místní nabídky do položky projektu. Položka nabídky se zobrazí, když uživatel klepne pravým tlačítkem myši na položku projektu v **Průzkumníka řešení**.

 Následující postup předpokládá, že jsou již definovány vlastní typ položky projektu služby SharePoint. Další informace najdete v tématu [jak: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).

### <a name="to-add-a-shortcut-menu-item-to-a-custom-project-item-type"></a>Přidání položky místní nabídky vlastního typu položky projektu

1. V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> událost *projectItemTypeDefinition* parametru.

2. V obslužné rutině události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> události, přidejte novou <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> nebo <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> kolekce parametr argumenty události.

3. V <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> obslužné rutiny události pro nové <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu, provádět úlohy, kterou chcete spustit, když uživatel vybere položku místní nabídky.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak přidat položka kontextové nabídky vlastního typu položky projektu. Když uživatel otevře místní nabídku položky projektu v **Průzkumníka řešení** a klikne **zapsat zprávu do okna výstup** položku nabídky, Visual Studio zobrazí zprávu v **výstupu**  okna.

 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypemenu.cs#4)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypemenu.vb#4)]

 Tento příklad používá k zápisu zprávy do projektu služby SharePoint **výstup** okna. Další informace najdete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje projekt knihovny tříd s odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint

- System.ComponentModel.Composition

## <a name="deploy-the-project-item"></a>Nasazení položky projektu
 Povolit ostatním vývojářům použít vaši položku projektu, vytvořte šablonu projektu nebo šablony položky projektu. Další informace najdete v tématu [položky vytvářet šablony a šablony projektů pro položky Sharepointového projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).

 K nasazení položky projektu, vytvořit [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení, šablony a další soubory, které chcete distribuovat do položky projektu. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Postupy: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)
- [Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)
- [Definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)
