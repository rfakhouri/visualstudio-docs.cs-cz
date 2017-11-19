---
title: "Postupy: zpracování konfliktů nasazení | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 8e545873-3fed-46cf-a95f-27b5fc0d5f83
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0ca793132fcf2f3e5e2a84d5289bcfb20f61d591
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-handle-deployment-conflicts"></a>Postupy: Zpracování konfliktů nasazení 
  Můžete zadat vlastní kód pro zpracování konfliktů nasazení pro položky projektu služby SharePoint. Například může určit, zda všechny soubory v položce aktuální projekt již existují v umístění nasazení a potom odstraňte nasazené soubory před nasazením aktuální položka projektu. Další informace o konflikty nasazení najdete v tématu [rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-handle-a-deployment-conflict"></a>Pro zpracování konfliktů nasazení  
  
1.  Vytváření rozšíření položky projektu, rozšíření projektu nebo definice nového typu položky projektu. Další informace naleznete v následujících tématech:  
  
    -   [Postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Postupy: vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Postupy: definování typu položky projektu služby SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  V rozšíření, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> objektu (v rozšíření položky projektu nebo rozšíření projektu) nebo <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> objektu (v definici nového typu položky projektu).  
  
3.  V obslužné rutině události určete, jestli je v konfliktu položka projektu, který se nasazuje a nasazené řešení na webu služby SharePoint na základě kritérií, které platí pro váš scénář. Můžete použít <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemEventArgs.ProjectItem%2A> vlastnosti parametru argumenty událostí k analýze položek projektu, který je nasazován a vy můžete analyzovat soubory v umístění nasazení voláním příkazu SharePoint, kterou definujete pro tento účel.  
  
     Pro mnoho typů je v konfliktu nejprve můžete určit se provádění kroků nasazení. Můžete to provést pomocí <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.DeploymentStepInfo%2A> vlastnost parametru argumentů události. I když obvykle má smysl ke zjištění konfliktu během integrované <xref:Microsoft.VisualStudio.SharePoint.Deployment.DeploymentStepIds.AddSolution> kroku nasazení, můžete zkontrolovat konflikty během jakéhokoli kroku nasazení.  
  
4.  Pokud došlo ke konfliktu, použijte <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> metodu <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.Conflicts%2A> vlastnost argumenty událostí pro vytvoření nového <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> objektu. Tento objekt představuje konflikt nasazení. Vaše volání <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> metoda, také zadat metodu, která je volána, chcete-li vyřešit konflikt.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje základní proces pro zpracování konfliktů nasazení v rozšíření položky projektu pro položky projektu definice seznamu. Pro zpracování konfliktů nasazení pro jiného typu položky projektu, předat jiný řetězec tak, aby <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Další informace najdete v tématu [rozšíření položky projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md).  
  
 Pro jednoduchost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> obslužné rutiny událostí v tomto příkladu předpokládá, že existuje konflikt nasazení (tedy vždy přidá novou <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> objektu) a `Resolve` metoda jednoduše vrátí **true** k označení, že Konflikt byl vyřešen. Ve scénáři skutečné vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> obslužné rutiny události byste nejprve určí, zda došlo ke konfliktu mezi soubor v položce aktuální projekt a soubor v umístění nasazení a poté přidejte <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> objektu pouze, pokud existuje konflikt. Například můžete použít `e.ProjectItem.Files` vlastnost v obslužné rutiny události pro analýzu souborů v položce projekt a může volání příkazu SharePoint k analýze soubory v umístění nasazení. Podobně ve scénáři skutečné `Resolve` může volání metody příkazu SharePoint vyřešení konfliktu na webu služby SharePoint. Další informace o vytváření SharePoint – příkazy najdete v tématu [postupy: vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../sharepoint/codesnippet/VisualBasic/deploymentconflict/extension/deploymentconflictextension.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../sharepoint/codesnippet/CSharp/deploymentconflict/extension/deploymentconflictextension.cs#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)   
 [Postupy: spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)   
 [Postupy: vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md)  
  
  