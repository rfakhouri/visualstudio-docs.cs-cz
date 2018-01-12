---
title: "Postupy: rozšíření uzlu služby SharePoint v Průzkumníku serveru | Microsoft Docs"
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
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d6fd079980897085f4e9c17a16dc57279ec586c2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-extend-a-sharepoint-node-in-server-explorer"></a>Postupy: Rozšíření uzlu služby SharePoint v průzkumníku serveru
  Můžete rozšířit uzly v rámci **připojení služby SharePoint** uzlu v **Průzkumníka serveru**. To je užitečné, pokud chcete přidat nové podřízené uzly, položky místní nabídky nebo vlastnosti do existujícího uzlu. Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
### <a name="to-extend-a-sharepoint-node-in-server-explorer"></a>Rozšíření uzlu služby SharePoint v Průzkumníku serveru  
  
1.  Vytvoření projektu knihovny tříd.  
  
2.  Přidejte odkazy na následující sestavení:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
    -   System.ComponentModel.Composition  
  
3.  Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> rozhraní.  
  
4.  Přidat <xref:System.ComponentModel.Composition.ExportAttribute> atribut třídy. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> typ do konstruktoru atributu.  
  
5.  Přidat <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> atribut třídy. Tento atribut určuje identifikátor řetězce pro typ uzlu, který chcete rozšířit.  
  
     Pokud chcete zadat typy předdefinovaný uzel poskytované sadě Visual Studio, předejte jednu z následujících hodnot výčtu konstruktoru atributu:  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: Použijte tyto hodnoty zadat uzlů připojení lokality (uzly, které zobrazují adresy URL), lokality uzlů nebo všechny ostatní nadřazené uzly v **Průzkumníka serveru**.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>: Použijte tyto hodnoty Pokud chcete zadat jednu z předdefinovaných uzly, které představuje jednotlivou součást na web služby SharePoint, jako je například uzel, který představuje seznam, pole nebo typ obsahu.  
  
6.  V implementaci <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> metoda, použijte členy *nodeType* parametr pro přidání funkcí do uzlu. Tento parametr je <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> objekt, který poskytuje přístup k událostí definovaných v <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> rozhraní. Například můžete zpracovávat následující události:  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested>: Zpracování této události do uzlu přidat nové podřízené uzly. Další informace najdete v tématu [postupy: Přidání vlastního uzlu služby SharePoint do Průzkumníka serveru](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md).  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeMenuItemsRequested>: Zpracování této události do uzlu přidat vlastní položku nabídky.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodePropertiesRequested>: Zpracování této události do uzlu přidat vlastní vlastnosti. Vlastnosti se zobrazí v **vlastnosti** okno, pokud je vybrán uzel.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak vytvořit dva různé typy rozšíření uzlu:  
  
-   Rozšíření, které přidá položky kontextové nabídky do uzlů serveru SharePoint. Když kliknete na položku nabídky, zobrazí název uzlu, který označeného.  
  
-   Rozšíření, které přidá vlastní vlastnost s názvem **ContosoExampleProperty** na každém uzlu, který reprezentuje pole s názvem **textu**.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#9](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextension.cs#9)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#9](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextension.vb#9)]  
  
 Toto rozšíření přidá vlastnost upravovat řetězec do uzlů. Můžete také vytvořit vlastní vlastnosti, které zobrazují jen pro čtení dat ze serveru SharePoint. Příklad, který ukazuje, jak to udělat, najdete v části [návod: rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
-   System.Windows.Forms  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 K nasazení **Průzkumníka serveru** rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přidání uzlu vlastní služby SharePoint do Průzkumníka serveru](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Návod: Rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Přidružení vlastních dat k rozšíření nástrojů služby SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  