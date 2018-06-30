---
title: Použití služby projektu SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project service
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2a74f2b7a2810a268c68306490dbbe2c197f0c72
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120168"
---
# <a name="use-the-sharepoint-project-service"></a>Použití služby projektu SharePoint
  Zahrnuje systému projektu služby SharePoint, můžete použít k provedení úlohy týkající se systému projektu služby projektu. Služba projektu je <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objektu.  
  
 Můžete získat přístup k projektu služby SharePoint v rozšíření nástrojů služby SharePoint. Můžete taky přejít do jiné typy rozšíření Visual Studia, jako je například doplňky a VSPackages. Další informace najdete v tématu [postupy: načtení služby projektu služby SharePoint](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md).  
  
## <a name="project-service-features"></a>Funkce služby projektu
 V následující tabulce jsou uvedeny úlohy, které můžete provádět pomocí projektu služby SharePoint a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> metody nebo vlastnosti používat k provádění jednotlivých úloh.  
  
|Úloha|Člen používat|  
|----------|-------------------|  
|Přístup k žádné projektu služby SharePoint, který je otevřen v sadě Visual Studio.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Projects%2A> Vlastnost.|  
|Přístup ke všem typů položek projektu služby SharePoint, které jsou k dispozici (včetně typů položek projektu předdefinované a vlastní).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.ProjectItemTypes%2A> Vlastnost.|  
|Přístup ke všem kroky nasazení, které jsou k dispozici do projektů služby SharePoint (včetně kroky předdefinované a vlastní nasazení).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.DeploymentSteps%2A> Vlastnost.|  
|Přístup k události, které se vyvolá, když vývojář refactors kódu v projektu služby SharePoint.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.CodeRefactoringEvents%2A> Vlastnost.|  
|Spuštění vlastní *příkazu SharePoint* , který volá do objektový model serveru SharePoint. Další informace o příkazech SharePoint, naleznete v části [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointConnection%2A> Vlastnost.|  
|Převést typ v systému projektu služby SharePoint k typu v sadě Visual Studio automatizace objektový model nebo integrace objektový model a naopak. Další informace najdete v tématu [převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> Metoda.|  
|Zápis zpráv do **výstup** okno nebo **seznam chyb** oken v sadě Visual Studio.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Logger%2A> Vlastnost.|  
|Přístup k dalším službám, které jsou k dispozici v sadě Visual Studio.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.ServiceProvider%2A> Vlastnost.|  
|Načtěte cestu ke složce instalace místního webu služby SharePoint, který se používá pro ladění řešení.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointInstallPath%2A> Vlastnost.|  
|Určit, zda [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] nebo [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] je nainstalován v počítači.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.IsSharePointInstalled%2A> Vlastnost.|  
|Ověřte funkce nebo balíček v řešení služby SharePoint.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.PackageValidationProvider%2A> Vlastnost.|  
  
## <a name="see-also"></a>Viz také:
 [Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Postupy: načtení služby projektu SharePoint](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [Rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Přehled modelu programování služby SharePoint rozšíření nástrojů](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)   
 [Postupy: načtení služby z objektu DTE](http://msdn.microsoft.com/library/bb166401.aspx)  
  
