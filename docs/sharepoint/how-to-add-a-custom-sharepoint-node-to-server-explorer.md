---
title: 'Postupy: Přidání vlastního uzlu služby SharePoint do Průzkumníka serveru | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8ece5c207a0244a55078ef44f9156e7e95cedf5c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60066491"
---
# <a name="how-to-add-a-custom-sharepoint-node-to-server-explorer"></a>Postupy: Přidání vlastního uzlu služby SharePoint do Průzkumníka serveru
  Můžete přidat vlastní uzly v rámci **připojení služby SharePoint** uzel v **Průzkumníka serveru**. To je užitečné, pokud chcete zobrazit další součásti služby SharePoint, které nejsou zobrazeny v **Průzkumníka serveru** ve výchozím nastavení. Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).

 Přidání vlastního uzlu nejprve vytvořte třídu, která definuje nový uzel. Pak vytvořte rozšíření, které přidá uzel jako podřízený objekt existující uzel.

### <a name="to-define-the-new-node"></a>Chcete-li definovat nový uzel

1. Vytvořte projekt knihovny tříd.

2. Přidejte odkazy na následující sestavení:

    - Microsoft.VisualStudio.SharePoint

    - Microsoft.VisualStudio.SharePoint.Explorer.Extensions

    - System.ComponentModel.Composition

    - System.Drawing

3. Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> rozhraní.

4. Přidejte do třídy následující atributy:

    - <xref:System.ComponentModel.Composition.ExportAttribute>. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> typ konstruktoru atributu.

    - <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute>. V definici uzlu tento atribut určuje identifikátor řetězce pro nový uzel. Doporučujeme použít formát *název společnosti*. *Název uzlu* abyste měli jistotu, že všechny uzly mají jedinečný identifikátor.

5. Ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider.InitializeType%2A> metody, použijte členy *typeDefinition* parametr konfigurace chování nový uzel. Tento parametr je <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition> objekt, který poskytuje přístup k události definované v <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents> rozhraní.

     Následující příklad kódu ukazuje, jak definovat nový uzel. Tento příklad předpokládá, že váš projekt obsahuje ikonu CustomChildNodeIcon jako vložený prostředek s názvem.

     [!code-vb[SPExtensibility.ProjectSystemExtension.General#6](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorernode.vb#6)]
     [!code-csharp[SPExtensibility.ProjectSystemExtension.General#6](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorernode.cs#6)]

### <a name="to-add-the-new-node-as-a-child-of-an-existing-node"></a>Chcete-li přidat nový uzel jako podřízený objekt existující uzel

1. Ve stejném projektu jako definice uzlu, vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> rozhraní.

2. Přidat <xref:System.ComponentModel.Composition.ExportAttribute> atribut třídy. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> typ konstruktoru atributu.

3. Přidat <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypeAttribute> atribut třídy. V uzlu Rozšíření tento atribut určuje identifikátor řetězce pro typ uzlu, který chcete rozšířit.

     Určení typů integrované uzlem poskytovaný sadou Visual Studio, předejte jeden z následujících hodnot výčtu konstruktoru atributu:

    - <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeTypes>: Použijte tyto hodnoty zadat uzlů připojení lokality (uzly, které zobrazují adresy URL), lokality, nebo všechny ostatní nadřazené uzlů v **Průzkumníka serveru**.

    - <xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.ExtensionNodeTypes>: Použijte tyto hodnoty určit jeden z předdefinovaných uzly, které představují jednotlivé součásti na Sharepointovém webu, jako je například uzel, který představuje seznam, pole nebo typ obsahu.

4. Ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension.Initialize%2A> metody, popisovač <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested> událost <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType> parametru.

5. V <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeEvents.NodeChildrenRequested> obslužná rutina události, přidání nového uzlu do kolekce podřízených uzlů <xref:Microsoft.VisualStudio.SharePoint.Explorer.ExplorerNodeEventArgs.Node%2A> objekt, který je zveřejněný prostřednictvím parametru argumentů události.

     Následující příklad kódu ukazuje, jak přidat nový uzel jako podřízený uzel webu služby SharePoint v **Průzkumníka serveru**.

     [!code-vb[SPExtensibility.ProjectSystemExtension.General#7](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorernode.vb#7)]
     [!code-csharp[SPExtensibility.ProjectSystemExtension.General#7](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorernode.cs#7)]

## <a name="complete-example"></a>Kompletní příklad
 Následující příklad kódu obsahuje kompletní kód k definování jednoduchého uzlu a přidejte ho jako podřízený uzel webu služby SharePoint v **Průzkumníka serveru**.

 [!code-vb[SPExtensibility.ProjectSystemExtension.General#5](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorernode.vb#5)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#5](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorernode.cs#5)]

## <a name="compiling-the-code"></a>Kompilování kódu
 Tento příklad předpokládá, že váš projekt obsahuje ikonu CustomChildNodeIcon jako vložený prostředek s názvem. Tento příklad také vyžaduje odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint

- System.ComponentModel.Composition

- System.Drawing

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 K nasazení **Průzkumníka serveru** rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)
- [Postupy: Rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)
- [Návod: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)
