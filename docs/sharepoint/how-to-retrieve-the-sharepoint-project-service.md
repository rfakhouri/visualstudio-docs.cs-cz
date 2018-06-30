---
title: 'Postupy: načtení služby projektu služby SharePoint | Microsoft Docs'
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
ms.openlocfilehash: 7e2dc633621734740065b8e0c80dd34795eac830
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120361"
---
# <a name="how-to-retrieve-the-sharepoint-project-service"></a>Postupy: načtení služby projektu SharePoint
  Mají přístup ke službě SharePoint projektu v následující typy řešení:  
  
-   Rozšíření systému projektu služby SharePoint, jako je například rozšíření projektu, rozšíření položky projektu nebo definici typu položky projektu. Další informace o těchto typech rozšíření najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).  
  
-   Rozšíření **připojení služby SharePoint** uzlu v **Průzkumníka serveru**. Další informace o těchto typech rozšíření najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
-   Jiný typ rozšíření sady Visual Studio, jako je například VSPackage.  
  
## <a name="retrieve-the-service-in-project-system-extensions"></a>Načtení služby v rozšíření systému projektu  
 V rozšíření systému projektu služby SharePoint, můžete přístup k projektu služby pomocí <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectService%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu.  
  
 Pomocí následujících postupů můžete také načíst služby projektu.  
  
#### <a name="to-retrieve-the-service-in-a-project-extension"></a>Načtení služby v rozšíření projektu  
  
1.  V implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> rozhraní, vyhledejte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> metoda.  
  
2.  Použití *projectService* parametr přístup ke službě.  
  
     Následující příklad kódu ukazuje, jak používat službu projektu zapsat zprávu do **výstup** okno a **seznam chyb** okna Jednoduchý projekt rozšíření.  
  
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#1](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.vb#1)]
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#1](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.cs#1)]  
  
     Další informace o vytváření rozšíření projektu najdete v tématu [postupy: vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
#### <a name="to-retrieve-the-service-in-a-project-item-extension"></a>Načtení služby v rozšíření položky projektu  
  
1.  V implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> rozhraní, vyhledejte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metoda.  
  
2.  Použití <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType.ProjectService%2A> vlastnost *projectItemType* parametr načtení služby.  
  
     Následující příklad kódu ukazuje, jak používat službu projektu zapsat zprávu do **výstup** okno a **seznam chyb** okna jednoduché rozšíření **definice seznamu** položka projektu.  
  
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#2](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.vb#2)]
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#2](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.cs#2)]  
  
     Další informace o vytváření rozšíření položky projektu najdete v tématu [postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
#### <a name="to-retrieve-the-service-in-a-project-item-type-definition"></a>Načtení služby v definici typu položky projektu  
  
1.  V implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní, vyhledejte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metoda.  
  
2.  Použití <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.ProjectService%2A> vlastnost *typeDefinition* parametr načtení služby.  
  
     Následující příklad kódu ukazuje, jak používat službu projektu zapsat zprávu do **výstup** okno a **seznam chyb** okno v definici typu položky projektu jednoduché.  
  
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#3](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.vb#3)]
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#3](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromprojectsystemextensions.getprojectservice/extension/extension.cs#3)]  
  
     Další informace o definování typů položek projektu najdete v tématu [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
## <a name="retrieve-the-service-in-server-explorer-extensions"></a>Načtení služby v rozšíření Průzkumníka serveru  
 V rozšíření **připojení služby SharePoint** uzlu v **Průzkumníka serveru**, mají přístup ke službě projekt pomocí <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.ServiceProvider%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> objektu.  
  
#### <a name="to-retrieve-the-service-in-a-server-explorer-extension"></a>Načtení služby v rozšíření Průzkumníka serveru  
  
1.  Získat <xref:System.IServiceProvider> objektu z <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.ServiceProvider%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> objekt v rozšíření.  
  
2.  Použití <xref:System.IServiceProvider.GetService%2A> metoda požádat o <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objektu.  
  
     Následující příklad kódu ukazuje, jak používat službu projektu zapsat zprávu do **výstup** okno a **seznam chyb** okna z místní nabídky, která přidá rozšíření do seznamu uzlů v **Průzkumníka serveru**.  
  
     [!code-vb[SPExtensibility.ProjectService.FromSPExplorerExtensions#1](../sharepoint/codesnippet/VisualBasic/spextensibility.projectservice.fromspexplorerextensions.getprojectservice/extension/extension.vb#1)]
     [!code-csharp[SPExtensibility.ProjectService.FromSPExplorerExtensions#1](../sharepoint/codesnippet/CSharp/spextensibility.projectservice.fromspexplorerextensions.getprojectservice/extension/extension.cs#1)]  
  
     Další informace o rozšíření **připojení služby SharePoint** uzlu v **Průzkumníka serveru**, najdete v části [postupy: rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
## <a name="retrieve-the-service-in-other-visual-studio-extensions"></a>Načtení služby v jiné rozšíření Visual Studia  
 Můžete načíst službu projektu ve VSPackage nebo v jakékoli rozšíření sady Visual Studio, který má přístup k <xref:EnvDTE80.DTE2> objektu v modelu objektu automatizace, jako je například Průvodce šablonou projektu, který implementuje <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní.  
  
 Ve VSPackage můžete požádat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objekt pomocí jedné z následujících metod:  
  
-   <xref:System.IServiceProvider.GetService%2A> Metoda spravovaného VSPackage, která je odvozena z <xref:Microsoft.VisualStudio.Shell.Package> třídy. Další informace najdete v tématu [jak: získat službu](../extensibility/how-to-get-a-service.md).  
  
-   Statické <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda. Další informace najdete v tématu [použití GetGlobalService](../extensibility/internals/service-essentials.md#how-to-use-getglobalservice).  
  
 V rozšíření sady Visual Studio, který má přístup k <xref:EnvDTE80.DTE2> objekt, můžete požádat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objekt pomocí <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> metodu <xref:Microsoft.VisualStudio.Shell.ServiceProvider> objektu. Další informace najdete v tématu [získávání služby z objektu DTE](../extensibility/how-to-get-a-service.md#getting-a-service-from-the-dte-object).  
  
## <a name="see-also"></a>Viz také:
 [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)   
 [Postupy: získání služby](../extensibility/how-to-get-a-service.md)   
 [Postupy: použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)  
  
