---
title: 'Postupy: Zpracování konfliktů nasazení | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 62e7740915d341eee1bbf5e112c4f09297c98be1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60066140"
---
# <a name="how-to-handle-deployment-conflicts"></a>Postupy: Zpracování konfliktů nasazení
  Můžete zadat vlastní kód pro zpracování konfliktů nasazení pro položku Sharepointového projektu. Například může určit, zda všechny soubory v aktuální položce projektu již existuje v umístění nasazení a pak odstraňte nasazených souborů před nasazením aktuální položky projektu. Další informace o konfliktech nasazení najdete v tématu [rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md).

### <a name="to-handle-a-deployment-conflict"></a>Zpracování konfliktů nasazení

1. Vytvoření rozšíření položky projektu, rozšíření projektu nebo definici novému typu položky projektu. Další informace naleznete v následujících tématech:

    - [Postupy: Vytváření rozšíření položky projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)

    - [Postupy: Vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)

    - [Postupy: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)

2. V rozšíření, zpracovat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> objekt (do rozšíření položky projektu nebo rozšíření projektu) nebo <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> objekt (v definici novému typu položky projektu).

3. V obslužné rutině události určete, zda je v konfliktu položky projektu, která se nasazuje a nasazené řešení na webu služby SharePoint na základě kritérií, které platí pro váš scénář. Můžete použít <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemEventArgs.ProjectItem%2A> vlastnost parametru argumentů události k analýze položky projektu, která se nasazuje a můžete analyzovat soubory v umístění nasazení voláním příkazu SharePoint, které definujete pro tento účel.

     Pro mnoho typů je v konfliktu nejprve můžete určit, který krok nasazení se provádí. Můžete to provést pomocí <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.DeploymentStepInfo%2A> vlastnost parametru argumenty události. I když je obvykle vhodné k detekci konfliktů během předdefinované <xref:Microsoft.VisualStudio.SharePoint.Deployment.DeploymentStepIds.AddSolution> krok nasazení, můžete vyhledat konflikty během libovolný krok nasazení.

4. Pokud došlo ke konfliktu, použijte <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> metodu <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs.Conflicts%2A> vlastností argumentů události k vytvoření nového <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> objektu. Tento objekt představuje konflikt nasazení. Ve volání <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflictCollection.Add%2A> metoda, také zadejte metodu, která je volána, jak vyřešit konflikt.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje základní proces pro zpracování konfliktů nasazení v rozšíření položky projektu pro položky projektu definice seznamu. Zpracování konfliktů nasazení pro jiný typ položky projektu, předat řetězec různých <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Další informace najdete v tématu [položek projektu služby SharePoint rozšiřte](../sharepoint/extending-sharepoint-project-items.md).

 Pro zjednodušení <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> obslužné rutiny události v tomto příkladu se předpokládá, že existuje konflikt nasazení (to znamená, ho vždy přidá nový <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> objektu) a `Resolve` jednoduše vrací metoda **true** označuje, že byl vyřešen konflikt. V reálné situaci vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> obslužné rutiny události by nejprve určit, zda došlo ke konfliktu mezi souborem v aktuální položce projektu a souboru lokality v umístění nasazení a pak přidejte <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentConflict> objektu pouze, pokud došlo ke konfliktu. Například můžete použít `e.ProjectItem.Files` vlastnost v obslužné rutině události pro analýzu souborů v položce projektu a můžete zavolat příkaz SharePoint, který chcete analyzovat soubory v umístění nasazení. Podobně ve scénáři skutečné `Resolve` metoda může volat příkaz SharePoint, jak vyřešit konflikt na webu služby SharePoint. Další informace o vytváření příkazů služby SharePoint, naleznete v tématu [jak: Vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md).

 [!code-vb[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../sharepoint/codesnippet/VisualBasic/deploymentconflict/extension/deploymentconflictextension.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.DeploymentConflict#1](../sharepoint/codesnippet/CSharp/deploymentconflict/extension/deploymentconflictextension.cs#1)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
- [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Postupy: Spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)
- [Postupy: Vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md)
