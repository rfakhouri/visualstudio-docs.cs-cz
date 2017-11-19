---
title: "Postupy: spuštění kódu při provádění kroků nasazení | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 6b0a52e5-e0ba-41bc-9e8a-1013e51fd3ba
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e1aed7e4fe7ee30450b3ec37ce36616648e830fa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-run-code-when-deployment-steps-are-executed"></a>Postupy: Spuštění kódu při provádění kroků nasazení
  Pokud chcete provádět další úkoly pro nasazení krok v projektu služby SharePoint, může zpracovávat události, které jsou vyvolány SharePoint – položky projektu před a po provedení každého kroku nasazení sady Visual Studio. Další informace najdete v tématu [rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-run-code-when-deployment-steps-are-executed"></a>Ke spuštění kódu při provádění kroků nasazení  
  
1.  Vytváření rozšíření položky projektu, rozšíření projektu nebo definice nového typu položky projektu. Další informace naleznete v následujících tématech:  
  
    -   [Postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Postupy: vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Postupy: definování typu položky projektu služby SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  V rozšíření, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> objektu (v rozšíření položky projektu nebo rozšíření projektu) nebo <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> objektu (v definici nového typu položky projektu).  
  
3.  V události obslužné rutiny, použijte <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs> a <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepCompletedEventArgs> parametry a získat informace o kroku nasazení. Například můžete určit, který krok nasazení provádí a jestli je řešení se nasazen nebo stažen.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak bude zpracováván <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> události v rozšíření pro seznam Instance položky projektu. Zapíše další zprávu pro toto rozšíření **výstup** okno při Visual Studio recykluje fond aplikací při nasazování a stahování řešení.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handledeploymentstepevents.vb#4)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handledeploymentstepevents.cs#4)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [Postupy: spuštění kódu při je projekt SharePoint nasazen nebo stažen](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)  
  
  