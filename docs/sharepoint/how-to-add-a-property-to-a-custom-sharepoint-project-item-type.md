---
title: "Postupy: Přidání vlastnosti do typu položky projektu služby SharePoint vlastní | Microsoft Docs"
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
ms.openlocfilehash: fa11cdfa8b46b6dcba889e00068676af5bdd5450
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-property-to-a-custom-sharepoint-project-item-type"></a>Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint
  Když definujete vlastní typu položky projektu služby SharePoint, můžete přidat vlastnost do položky projektu. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníku řešení**.  
  
 Následující postup předpokládá, že jste již definovali vlastního typu položky projektu služby SharePoint. Další informace najdete v tématu [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
### <a name="to-add-a-property-to-a-definition-of-a-project-item-type"></a>Přidání vlastnosti do definice vlastního typu položky projektu  
  
1.  Definice třídy s veřejnou vlastnost, která představuje vlastnost, kterou přidáváte do vlastního typu položky projektu. Pokud chcete přidat více vlastností vlastního typu položky projektu, můžete definovat všechny vlastnosti v stejné třídy nebo různých tříd.  
  
2.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> události *projectItemTypeDefinition* parametr.  
  
3.  V obslužné rutiny události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> událostí, přidá instanci třídy vašich vlastních vlastností do <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> kolekce parametru argumentů události.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat vlastnost s názvem **Příklad vlastnosti** na vlastní položky projektu typu.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#11)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#11)]  
  
### <a name="understanding-the-code"></a>Pochopení kódu  
 Zajistit, aby stejnou instanci systému `CustomProperties` třída se používá pokaždé, když <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> dojde k události, ukázkový kód uloží objekt vlastnosti, který má <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost položky první projektu, když dojde k této události. Kód načte tento objekt vždy, když dojde znovu k této události. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> najdete v části Vlastnosti pro uložení dat s položky projektu [přidružení vlastních dat k rozšíření nástrojů SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 K zachování změn na hodnotu vlastnosti **nastavit** přistupujícího `ExampleProperty` uloží novou hodnotu na <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objekt, který je přidružen vlastnost. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> najdete v části Vlastnosti pro uložení dat s položky projektu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>Určení chování vlastní vlastnosti  
 Můžete definovat jak vlastní vlastnosti se zobrazí a chovají v **vlastnosti** okna s použitím atributů z <xref:System.ComponentModel> obor názvů pro definování vlastnosti. Následující atributy jsou užitečné v mnoha scénářích:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Určuje název vlastnosti, které se zobrazí v **vlastnosti** okno.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Určuje popis řetězec, který se zobrazí v dolní části **vlastnosti** okno, pokud je vybrána vlastnost.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Určuje výchozí hodnotu vlastnosti.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Určuje vlastní převod mezi řetězec, který se zobrazí v **vlastnosti** okno a hodnotu vlastnosti jiné než řetězec.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Určuje vlastní editor k úpravě vlastnost.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tyto příklady kódu vyžadovat projektu knihovny tříd s odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>Položka projektu nasazení  
 Pokud chcete povolit jiné vývojářům používat vaše položky projektu, vytvořte šablona projektu nebo šablony položek projektu. Další informace najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Chcete-li nasadit položku projektu, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení, šablony a další soubory, které chcete distribuovat do položky projektu. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: definování typu položky projektu služby SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Postupy: Přidání položky místní nabídky do typu položky projektu služby SharePoint vlastní](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  