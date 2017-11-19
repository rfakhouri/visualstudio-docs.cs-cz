---
title: "Postupy: Přidání vlastnosti do rozšíření položky projektu služby SharePoint | Microsoft Docs"
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
ms.assetid: 4fd97ef2-86e7-4d92-8e34-5b0ec3cc43a0
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 51b75626a76778c5f00ed9408950f999133209dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-property-to-a-sharepoint-project-item-extension"></a>Postupy: Přidání vlastnosti do rozšíření položky projektu SharePoint
  Rozšíření položky projektu můžete použít k přidání vlastnosti do položky projektu služby SharePoint, který už je nainstalovaný v sadě Visual Studio. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníku řešení**.  
  
 Následující postup předpokládá, že jste již vytvořili rozšíření položky projektu. Další informace najdete v tématu [postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
### <a name="to-add-a-property-to-a-project-item-extension"></a>Přidání vlastnosti do rozšíření položky projektu  
  
1.  Definice třídy s veřejnou vlastnost, která představuje vlastnost, kterou přidáváte do typu položky projektu. Pokud chcete přidat více vlastností typu položky projektu, můžete definovat všechny vlastnosti v stejné třídy nebo různých tříd.  
  
2.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> události *projectItemType* parametr.  
  
3.  V obslužné rutiny události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> událostí, přidejte instance třídy vlastnosti k <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> kolekce parametru argumentů události.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat vlastnost s názvem **Příklad vlastnosti** do položky projektu přijímač událostí.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#8](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionproperty.cs#8)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#8](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionproperty.vb#8)]  
  
### <a name="understanding-the-code"></a>Pochopení kódu  
 Zajistit, aby stejnou instanci systému `CustomProperties` třída se používá pokaždé, když <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> dojde k události, příklad kódu přidá vlastnosti objekt, který má <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost položky první projektu, když dojde k této události. Kód načte tento objekt vždy, když dojde znovu k této události. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost pro přidružení dat k položky projektu, najdete v části [přidružení vlastních dat k rozšíření nástrojů SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 K zachování změn na hodnotu vlastnosti **nastavit** přistupujícího `ExampleProperty` uloží novou hodnotu na <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objekt, který je přidružen vlastnost. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> najdete v části Vlastnosti pro uložení dat s položky projektu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>Určení chování vlastní vlastnosti  
 Můžete definovat jak vlastní vlastnosti se zobrazí a chovají v **vlastnosti** okna s použitím atributů z <xref:System.ComponentModel> obor názvů pro definování vlastnosti. Následující atributy jsou užitečné v mnoha scénářích:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Určuje název vlastnosti, které se zobrazí v **vlastnosti** okno.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Určuje popis řetězec, který se zobrazí v dolní části **vlastnosti** okno, pokud je vybrána vlastnost.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Určuje výchozí hodnotu vlastnosti.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Určuje vlastní převod mezi řetězec, který se zobrazí v **vlastnosti** okno a hodnotu vlastnosti jiné než řetězec.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Určuje vlastní editor k úpravě vlastnost.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tyto příklady vyžadují projektu knihovny tříd s odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Postupy: Přidání položky místní nabídky do rozšíření položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)   
 [Návod: Rozšiřování typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  