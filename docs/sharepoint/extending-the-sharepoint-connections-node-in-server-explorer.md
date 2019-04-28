---
title: Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6b1d461419497a0a45f50f12589cf3ac978a7666
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967354"
---
# <a name="extend-the-sharepoint-connections-node-in-server-explorer"></a>Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru
  V sadě Visual Studio, můžete připojit k místní weby služby SharePoint ve vývojovém počítači s použitím **připojení služby SharePoint** uzlu **Průzkumníka serveru** okna. Tento uzel zobrazuje řadu součástí místní weby služby SharePoint v hierarchickém stromovém zobrazení. Například můžete zobrazit seznamy, knihovny dokumentů a typy obsahu na místních serverech. Další informace o používání **Průzkumníka serveru** pro připojení k místním webům služby SharePoint, naleznete v tématu [připojení SharePoint procházet pomocí Průzkumníka serveru](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md).

 Můžete rozšířit **připojení služby SharePoint** uzlu tak, že vytvoříte rozšíření pro existující uzly, nebo vytvořením vlastního typu uzlu a jejich přidání do hierarchie uzlů.

## <a name="tasks-for-extending-the-sharepoint-connections-node"></a>Úlohy pro rozšíření uzlu připojení služby SharePoint
 K rozšíření existující uzel, vytvořit rozšíření sady Visual Studio, který implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> rozhraní. Když rozšíříte uzel, můžete přidat funkce do uzlu například vlastní položky místní nabídky nebo vlastní vlastnosti. Další informace najdete v tématu [jak: Rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).

 Pokud chcete vytvořit vlastní typ uzlu, vytvořit rozšíření sady Visual Studio, který implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> rozhraní. Vytvořit vlastní uzel, pokud chcete zobrazit součásti Sharepointové weby, které nejsou zobrazeny v **Průzkumníka serveru** ve výchozím nastavení. Například **Průzkumníka serveru** nemá zobrazovat galerii webových částí webu pro službu SharePoint ve výchozím nastavení, ale můžete přidat vlastní uzel, který to dělá. Další informace najdete v tématu [jak: Přidání vlastního uzlu služby SharePoint do Průzkumníka serveru](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md) a [názorný postup: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).

## <a name="add-custom-properties-to-nodes"></a>Přidání vlastních vlastností do uzlů
 Když rozšíření uzlu nebo vytvořit vlastní typ uzlu, můžete přidat vlastní vlastnosti k uzlu. Vlastnosti se zobrazí v **vlastnosti** okno při výběru uzlu.

 Existují dva typy vlastních vlastností, které přidáte do uzlu:

- Vlastnosti, které zobrazují sadu jen pro čtení dat z webu služby SharePoint. Popisuje data součást služby SharePoint, která představuje uzel. Názorný postup ukazuje, jak to provést, najdete v části [názorný postup: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).

- Vlastnosti, které zobrazují data vlastní čtení a zápisu. Příklad kódu ukazuje, jak to provést, najdete v části [jak: Rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).

## <a name="get-data-for-built-in-nodes"></a>Získání dat pro integrované uzly
 Všechny integrované uzly poskytovaný sadou Visual Studio obsahují některá data o součást služby SharePoint, které představují. Například uzel, který představuje seznam na webu služby SharePoint poskytuje data o seznamu, jako jsou název a adresu URL výchozí zobrazení seznamu.

 Pro přístup k těmto datům, načíst datový objekt z <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> objekt, který představuje uzel vás zajímají. Typ datového objektu závisí na typu uzlu.

 Následující příklad kódu ukazuje, jak získat objekt data pro seznam uzlů. Tento příklad v rámci většího příkladu najdete v tématu [jak: Získání dat pro předdefinovaný uzel služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md).

 [!code-vb[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#11)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#11)]

 Následující tabulka uvádí typy datových objektů pro každý typ integrované uzlem.

|Typ uzlu|Datový typ objektu|
|---------------|----------------------|
|Uzel webu služby SharePoint|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerSiteNodeInfo>|
|Typ obsahu|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IContentTypeNodeInfo>|
|Funkce|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFeatureNodeInfo>|
|Pole|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFieldNodeInfo>|
|Seznam|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListNodeInfo>|
|Šablona seznamu|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListTemplateNodeInfo>|
|Zobrazení seznamu (Microsoft.SharePoint.SPView)|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListViewNodeInfo>|
|Přidružení pracovního postupu|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowAssociationNodeInfo>|
|Šablona pracovního postupu|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowTemplateNodeInfo>|

 Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost, naleznete v tématu [rozšíření nástrojů přidružení vlastních dat se Sharepointem](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).

## <a name="see-also"></a>Viz také:
- [Návod: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)
- [Postupy: Rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)
- [Postupy: Přidání vlastního uzlu služby SharePoint do Průzkumníka serveru](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)
- [Postupy: Získání dat pro předdefinovaný uzel služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)
- [Přidružení vlastních dat k rozšíření nástrojů SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)
- [Procházet připojení služby SharePoint pomocí Průzkumníka serveru](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)
- [Rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)
