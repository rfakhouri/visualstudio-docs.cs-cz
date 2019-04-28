---
title: 'Postupy: Přidání vlastnosti do rozšíření položky projektu služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 20a7abaa8c132b3cd1679ab95ed8154b8ca86502
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967224"
---
# <a name="how-to-add-a-property-to-a-sharepoint-project-item-extension"></a>Postupy: Přidání vlastnosti do rozšíření položky projektu SharePoint
  Rozšíření položky projektu můžete použít k přidání vlastnosti do položky projektu služby SharePoint, která je již nainstalována v sadě Visual Studio. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníka řešení**.

 Následující postup předpokládá, že jste již vytvořili rozšíření položky projektu. Další informace najdete v tématu [jak: Vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).

### <a name="to-add-a-property-to-a-project-item-extension"></a>Přidání vlastnosti do rozšíření položky projektu

1. Definice třídy s veřejné vlastnosti, která představuje vlastnost, kterou chcete přidat do typu položky projektu. Pokud chcete přidat více vlastností typu položky projektu, můžete definovat všechny vlastnosti ve stejné třídě nebo v různých tříd.

2. V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> událost *projectItemType* parametru.

3. V obslužné rutině události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> události, přidá instanci třídy vlastnosti má <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> kolekce parametr argumenty události.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak přidat vlastnost s názvem **Příklad vlastnosti** do položky projektu příjemce událostí.

 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#8](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionproperty.cs#8)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#8](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionproperty.vb#8)]

### <a name="understand-the-code"></a>Vysvětlení kódu
 Chcete-li zajistit stejnou instanci `CustomProperties` třída se používá pokaždé, když <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> dojde k události, příklad kódu přidá vlastnosti objektu <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnosti položky projektu, když dojde k této události. Kód načte tento objekt pokaždé, když se tato událost bude opakovat. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost pro přidružení data s položkami projektu, viz [rozšíření nástrojů přidružení vlastních dat se Sharepointem](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).

 K uchování změn na hodnotu vlastnosti **nastavit** přístupový objekt pro `ExampleProperty` uloží novou hodnotu na <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objekt, který je přidružený vlastnost. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost k uchování dat s položkami projektu, viz [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).

### <a name="specify-the-behavior-of-custom-properties"></a>Zadejte chování vlastní vlastnosti
 Můžete definovat, jak vlastní vlastnosti se zobrazí a jak se bude chovat v **vlastnosti** okna s použitím atributů z <xref:System.ComponentModel> oboru názvů v definici vlastnosti. Následující atributy jsou užitečné v mnoha scénářích:

- <xref:System.ComponentModel.DisplayNameAttribute>: Určuje název vlastnosti, která se zobrazí **vlastnosti** okna.

- <xref:System.ComponentModel.DescriptionAttribute>: Určuje řetězec popisu, který se zobrazí v dolní části **vlastnosti** okno, pokud je vybrána vlastnost.

- <xref:System.ComponentModel.DefaultValueAttribute>: Určuje výchozí hodnotu vlastnosti.

- <xref:System.ComponentModel.TypeConverterAttribute>: Určuje vlastní převod mezi řetězci, který se zobrazí v **vlastnosti** okna a hodnotu vlastnosti jiné než řetězec.

- <xref:System.ComponentModel.EditorAttribute>: Určuje vlastní editor použít ke změně vlastnosti.

## <a name="compile-the-code"></a>Kompilace kódu
 Tyto příklady vyžadují projekt knihovny tříd s odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Postupy: Vytváření rozšíření položky projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)
- [Postupy: Přidání položky místní nabídky do rozšíření položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)
- [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Návod: Rozšíření typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)
