---
title: Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio | Microsoft Docs
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 64de38fe796ce3c1e0d333a22582ad2973e1c4d2
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765356"
---
# <a name="convert-between-sharepoint-project-system-types-and-other-visual-studio-project-types"></a>Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio
  V některých případech může mít objekt v systému projektu služby SharePoint a chcete používat funkce odpovídající objektu v sadě Visual Studio automatizace objektový model nebo integrace objektový model, nebo naopak. V těchto případech můžete použít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> metoda projektu služby SharePoint převést objekt na jiný objekt modelu.  
  
 Například můžete mít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu, ale chcete použít metody, které jsou dostupné jenom na <xref:EnvDTE.Project> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> objektu. V takovém případě můžete použít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> způsobů, jak převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> k <xref:EnvDTE.Project> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>.  
  
 Další informace o sadě Visual Studio automatizace objektový model a model objektu integrace sady Visual Studio najdete v tématu [přehled programovací Model z rozšíření nástrojů SharePoint](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).  
  
## <a name="types-of-conversions"></a>Převody typů
 Následující tabulka uvádí typy, které tuto metodu můžete přepínat mezi systému projektu služby SharePoint a jinými modely objekt sady Visual Studio.  
  
|Typ systému projektu služby SharePoint|Odpovídající typy v objektové modely automatizace a integrace|  
|------------------------------------|-------------------------------------------------------------------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>|<xref:EnvDTE.Project><br /><br /> or<br /><br /> Žádné rozhraní v sadě Visual Studio integrace objektový model, který je implementováno modulem základní objekt COM pro projekt. Tato rozhraní zahrnují <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> (nebo odvozené rozhraní), a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>. Seznam hlavních rozhraní, které implementují projekty najdete v tématu [základní součásti služby projektu modelu](/visualstudio/extensibility/internals/project-model-core-components).|  
|<xref:Microsoft.VisualStudio.SharePoint.IMappedFolder><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>|<xref:EnvDTE.ProjectItem><br /><br /> or<br /><br /> A<xref:System.UInt32> hodnotu (také nazývané VSITEMID), který identifikuje člena v projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> který ji obsahuje. Tato hodnota může být předán *itemid* parametr některých <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> metody.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak používat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> způsobů, jak převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> do objektu <xref:EnvDTE.Project>.  
  
 [!code-csharp[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/CSharp/spprojectserviceaddin/connect.cs#2)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/VisualBasic/spprojectserviceaddin/connect.vb#2)]  
  
 Tento příklad vyžaduje:  
  
-   Rozšíření systému projektu služby SharePoint, který obsahuje odkaz na *EnvDTE.dll* sestavení. Další informace najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).  
  
-   Kód, který registruje `projectService_ProjectAdded` metodu ke zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objektu. Příklad, naleznete v části [postupy: vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
## <a name="see-also"></a>Viz také:
 [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)   
 [Postupy: načtení služby projektu SharePoint](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [Přehled modelu programování rozšíření nástrojů služby SharePoint](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
