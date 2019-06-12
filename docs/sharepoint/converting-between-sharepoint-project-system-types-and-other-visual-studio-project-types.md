---
title: 'Převeďte: Systém typů projektu služby SharePoint do/z jiných typů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project service
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 40ea60a8df5bc0bcd033c60a83d742ed3249cc53
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2019
ms.locfileid: "66836001"
---
# <a name="convert-between-sharepoint-project-system-types-and-other-visual-studio-project-types"></a>Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio
  V některých případech můžete mít objekt v systému projektu služby SharePoint a chcete používat funkce odpovídajícího objektu v modelu objektu automatizace sady Visual Studio nebo integrace objektový model, nebo naopak. V těchto případech můžete použít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> metoda projektu služby SharePoint pro převod objektu na jiný objekt modelu.

 Například můžete mít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu, ale chcete použít metody, které jsou dostupné jenom na <xref:EnvDTE.Project> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> objektu. V takovém případě můžete použít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> způsobů, jak převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> do <xref:EnvDTE.Project> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>.

 Další informace o modelu objektu automatizace sady Visual Studio a Visual Studio integrace objektový model, najdete v části [Přehled programovacího modelu SharePoint rozšíření nástrojů](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).

## <a name="types-of-conversions"></a>Typy převodů
 Následující tabulka uvádí typy, které tato metoda nemůže provést převod mezi systému Sharepointových projektů a další modely objektů sady Visual Studio.

|Typ systému projektu služby SharePoint|Odpovídajících typů v modely objektů automatizace a integrace|
|------------------------------------|-------------------------------------------------------------------------|
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>|<xref:EnvDTE.Project><br /><br /> or<br /><br /> Každé rozhraní v objektovém modelu služby Visual Studio integrace, který je implementováno prostřednictvím základní objekt modelu COM pro projekt. Tato rozhraní zahrnují <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> (nebo odvozené rozhraní), a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>. Seznam hlavní rozhraní, které implementují projektů, naleznete v tématu [základní komponenty modelu projektu](../extensibility/internals/project-model-core-components.md).|
|<xref:Microsoft.VisualStudio.SharePoint.IMappedFolder><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>|<xref:EnvDTE.ProjectItem><br /><br /> or<br /><br /> A<xref:System.UInt32> hodnotu (také nazývané VSITEMID), která identifikuje člena v projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> , který jej obsahuje. Tato hodnota může být předán *itemid* parametr některých <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> metody.|

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak používat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> způsobů, jak převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu <xref:EnvDTE.Project>.

 [!code-csharp[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/CSharp/spprojectserviceaddin/connect.cs#2)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/VisualBasic/spprojectserviceaddin/connect.vb#2)]

 Tento příklad vyžaduje:

- Rozšíření systému projektu služby SharePoint, který obsahuje odkaz na *EnvDTE.dll* sestavení. Další informace najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).

- Kód, který se registruje `projectService_ProjectAdded` metodu ke zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objektu. Příklad najdete v tématu [jak: Vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).

## <a name="see-also"></a>Viz také:

- [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)
- [Postupy: Načtení služby projektu SharePoint](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)
- [Přehled programovacího modelu SharePoint rozšíření nástrojů](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)
