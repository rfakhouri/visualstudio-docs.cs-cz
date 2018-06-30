---
title: 'Postupy: spuštění kódu při je projekt SharePoint nasazen nebo stažen | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4fa7d2652e65e26686a5058fcb2c8f5130fbbdde
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120270"
---
# <a name="how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>Postupy: spuštění kódu pokud je projekt SharePoint nasazen nebo stažen
  Pokud chcete provést další úlohy, v případě, že je projekt SharePoint nasazen nebo stažen, může zpracovávat události, které jsou vyvolány Visual Studio. Další informace najdete v tématu [balení a nasazení SharePoint rozšířit](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-run-code-when-a-sharepoint-project-is-deployed-or-retracted"></a>Ke spuštění kódu Pokud projekt SharePoint nasazen nebo stažen  
  
1.  Vytváření rozšíření položky projektu, rozšíření projektu nebo definice nového typu položky projektu. Další informace naleznete v následujících tématech:  
  
    -   [Postupy: vytváření rozšíření položky projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Postupy: vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  V rozšíření, přístup <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objektu. Další informace najdete v tématu [postupy: načtení služby projektu služby SharePoint](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md).  
  
3.  Zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentStarted> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentCompleted> události služby projektu.  
  
4.  V události obslužné rutiny, použijte <xref:Microsoft.VisualStudio.SharePoint.DeploymentEventArgs> parametr a získat informace o nasazení aktuální relace. Například můžete určit, který projekt je v aktuální relaci nasazení a zda je právě nasazen nebo stažen.  
  
 Následující příklad kódu ukazuje, jak bude zpracováván <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentStarted> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.DeploymentCompleted> události v rozšíření projektu. Zapíše další zprávu pro toto rozšíření **výstup** okno při spuštění nasazení a dokončení projektu služby SharePoint.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#12](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handleprojectdeploymentevents.cs#12)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#12](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handleprojectdeploymentevents.vb#12)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Postupy: spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)  
  
