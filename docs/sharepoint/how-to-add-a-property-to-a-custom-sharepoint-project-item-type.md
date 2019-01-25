---
title: 'Postupy: Přidání vlastnosti typu položky projektu SharePoint vlastní | Dokumentace Microsoftu'
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
ms.openlocfilehash: ca3bfbf6ecd773f0a7c3147a44eb02a5c260764b
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54872791"
---
# <a name="how-to-add-a-property-to-a-custom-sharepoint-project-item-type"></a>Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint
  Při definování vlastního typu položky projektu služby SharePoint, můžete přidat vlastnost do položky projektu. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníka řešení**.  
  
 Následující postup předpokládá, že jsou již definovány vlastní typ položky projektu služby SharePoint. Další informace najdete v tématu [jak: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
### <a name="to-add-a-property-to-a-definition-of-a-project-item-type"></a>Přidání vlastnosti do definice typu položky projektu  
  
1.  Definice třídy s veřejné vlastnosti, která představuje vlastnost, kterou přidáváte vlastního typu položky projektu. Pokud chcete přidat více vlastností vlastního typu položky projektu, můžete definovat všechny vlastnosti ve stejné třídě nebo v různých tříd.  
  
2.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> událost *projectItemTypeDefinition* parametru.  
  
3.  V obslužné rutině události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> události, přidá instanci třídy vašich vlastních vlastností do <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> kolekce parametr argumenty události.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat vlastnost s názvem **Příklad vlastnosti** k vlastní položky projektu typu.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#11)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#11)]  
  
### <a name="understand-the-code"></a>Vysvětlení kódu  
 Chcete-li zajistit stejnou instanci `CustomProperties` třída se používá pokaždé, když <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> dojde k události, ukázkový kód uloží objekt vlastností <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnosti položky projektu, když dojde k této události. Kód načte tento objekt pokaždé, když se tato událost bude opakovat. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost pro uložení dat se položky projektu, viz [rozšíření nástrojů přidružení vlastních dat se Sharepointem](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 K uchování změn na hodnotu vlastnosti **nastavit** přístupový objekt pro `ExampleProperty` uloží novou hodnotu na <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objekt, který je přidružený vlastnost. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost k uchování dat s položkami projektu, viz [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specify-the-behavior-of-custom-properties"></a>Zadejte chování vlastní vlastnosti  
 Můžete definovat, jak vlastní vlastnosti se zobrazí a jak se bude chovat v **vlastnosti** okna s použitím atributů z <xref:System.ComponentModel> oboru názvů v definici vlastnosti. Následující atributy jsou užitečné v mnoha scénářích:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Určuje název vlastnosti, která se zobrazí **vlastnosti** okna.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Určuje řetězec popisu, který se zobrazí v dolní části **vlastnosti** okno, pokud je vybrána vlastnost.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Určuje výchozí hodnotu vlastnosti.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Určuje vlastní převod mezi řetězci, který se zobrazí v **vlastnosti** okna a hodnotu vlastnosti jiné než řetězec.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Určuje vlastní editor použít ke změně vlastnosti.  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tyto příklady kódu vyžadují projekt knihovny tříd s odkazy na následující sestavení:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-project-item"></a>Nasazení položky projektu  
 Povolit ostatním vývojářům použít vaši položku projektu, vytvořte šablonu projektu nebo šablony položky projektu. Další informace najdete v tématu [položky vytvářet šablony a šablony projektů pro položky Sharepointového projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 K nasazení položky projektu, vytvořit [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení, šablony a další soubory, které chcete distribuovat do položky projektu. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Postupy: Přidání položky místní nabídky do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
