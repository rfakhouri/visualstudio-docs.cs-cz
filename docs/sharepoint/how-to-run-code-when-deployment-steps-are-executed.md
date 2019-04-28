---
title: 'Postupy: Spuštění kódu při nasazení provádění kroků | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 581f9c0b9907fd59863f6a468a45ef67d9966475
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62813149"
---
# <a name="how-to-run-code-when-deployment-steps-are-executed"></a>Postupy: Spuštění kódu při provádění kroků nasazení
  Pokud chcete provádět další úkoly pro krok nasazení v projektu služby SharePoint, můžete zpracovávat události, které jsou vyvolány pomocí položky Sharepointového projektu před a po provedení každého kroku nasazení sady Visual Studio. Další informace najdete v tématu [rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md).

### <a name="to-run-code-when-deployment-steps-are-executed"></a>Ke spuštění kódu při provádění kroků nasazení

1. Vytvoření rozšíření položky projektu, rozšíření projektu nebo definici novému typu položky projektu. Další informace naleznete v následujících tématech:

    - [Postupy: Vytváření rozšíření položky projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)

    - [Postupy: Vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)

    - [Postupy: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)

2. V rozšíření, zpracovat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> objekt (do rozšíření položky projektu nebo rozšíření projektu) nebo <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> objekt (v definici novému typu položky projektu).

3. V události obslužné rutiny, použijte <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs> a <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepCompletedEventArgs> parametry a získat informace o kroku nasazení. Například můžete určit, který krok nasazení se provádí a řešení určuje, zda je právě nasazen nebo stažen.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak zpracovat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> události v rozšíření pro položky projektu instanci seznamu. Toto rozšíření zapíše na další zprávu **výstup** okno dojde k sadě Visual Studio recyklování fondu aplikací při nasazování a odvolává se řešení.

 [!code-vb[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handledeploymentstepevents.vb#4)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handledeploymentstepevents.cs#4)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
- [Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)
- [Postupy: Spuštění kódu pokud je projekt SharePoint nasazen nebo stažen](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)
