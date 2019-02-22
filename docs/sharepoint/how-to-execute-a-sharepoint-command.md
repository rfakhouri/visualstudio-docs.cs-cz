---
title: 'Postupy: Provedení příkazu SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint commands [SharePoint development in Visual Studio], executing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: db95754fd27820e0686f65a22393f51510467fb6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56631182"
---
# <a name="how-to-execute-a-sharepoint-command"></a>Postupy: Provedení příkazu SharePoint
  Pokud chcete použít objektový model serveru v rozšíření nástrojů služby SharePoint, je třeba vytvořit vlastní *příkaz serveru SharePoint* pro volání rozhraní API. Po definování příkazu a nasazení pomocí rozšíření nástrojů služby SharePoint, rozšíření můžete spustit příkaz provést volání do objektového modelu serveru SharePoint. Chcete-li spustit příkaz, použijte jednu z metod ExecuteCommand <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> objektu.

 Další informace o účelu příkazů služby SharePoint, naleznete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).

### <a name="to-execute-a-sharepoint-command"></a>K provedení příkazu SharePoint

1.  V rozšíření nástrojů služby SharePoint, získáte <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> objektu. Způsob, jak můžete získat <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> objektu závisí na typu rozšíření při vytváření:

    -   V rozšíření systému projektu služby SharePoint, použijte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.SharePointConnection%2A> vlastnost.

         Další informace o rozšíření systému projektu naleznete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).

    -   V rozšíření **připojení služby SharePoint** uzel v **Průzkumníka serveru**, použijte <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeContext.SharePointConnection%2A> vlastnost. Chcete-li získat <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeContext> objektu, použijte <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.Context%2A> vlastnost.

         Další informace o **Průzkumníka serveru** rozšíření, naleznete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).

    -   V kódu, který není součástí rozšíření nástrojů služby SharePoint, jako je Průvodce šablonou projektu, použijte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointConnection%2A> vlastnost.

         Další informace o načtení služby projektu naleznete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

2.  Volat jednu z metod ExecuteCommand <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> objektu. Předejte název příkazu, který chcete spustit na první argument metody ExecuteCommand. Pokud váš příkaz má vlastní parametr, předejte parametr druhý argument metody ExecuteCommand.

     Existuje jiný ExecuteCommand přetížení pro každou podporovanou signaturu příkazu. Následující tabulka uvádí podporované podpisy a které přetížení pro každý podpis.

    |Příkaz podpis|Parametr ExecuteCommand přetížení pro použití|
    |-----------------------|------------------------------------|
    |Příkaz má jako výchozí uplatněna pouze <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> parametr a žádnou návratovou hodnotu.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|
    |Příkaz má jako výchozí uplatněna pouze <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> parametrů a návratové hodnoty.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|
    |Příkaz má dva parametry (výchozí hodnota <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> parametr a vlastní parametr) a návratovou hodnotu.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|
    |Příkaz má dva parametry a návratové hodnoty.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak používat <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A> přetížení volání `Contoso.Commands.UpgradeSolution` příkaz, který je popsaný v [jak: Vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md).

 [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#6](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/upgradestep.cs#6)]
 [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#6](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/upgradestep.vb#6)]

 `Execute` Metodu uvedenou v tomto příkladu je implementace <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep.Execute%2A> metodu <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> rozhraní v vlastního kroku nasazení. Tento kód v rámci většího příkladu najdete v tématu [názorný postup: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).

 Mějte na paměti následující podrobnosti o volání <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A> metody:

-   První parametr určuje příkaz, který chcete volat. Tento řetězec odpovídá hodnotě, kterou předat <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute> v definici příkazu.

-   Druhý parametr je hodnota, kterou chcete předat vlastní druhý parametr příkazu. V takovém případě je úplná cesta *.wsp* soubor, který se upgraduje na webu služby SharePoint.

-   Kód nepředává implicitní <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> parametr k příkazu. Tento parametr je předán do příkaz automaticky při volání příkazu z rozšíření systému projektu služby SharePoint nebo rozšířením **připojení služby SharePoint** uzel v **Průzkumníka serveru**. V jiných typech řešení, jako je například Průvodce pro šablony projektu, který implementuje <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní, tento parametr je **null**.

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje odkaz na sestavení Microsoft.VisualStudio.SharePoint.

## <a name="see-also"></a>Viz také:
- [Volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md)
- [Postupy: Vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md)
- [Návod: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)
