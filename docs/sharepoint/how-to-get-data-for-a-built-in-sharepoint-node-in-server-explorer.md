---
title: 'Postupy: získání dat pro předdefinovaný uzel služby SharePoint v Průzkumníku serveru | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f448ec8d7cfe22495aa3f7b2ce9191f106205c33
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer"></a>Postupy: Získání dat pro předdefinovaný uzel služby SharePoint v průzkumníku serveru
  Pro každý předdefinovaný uzel služby SharePoint v **Průzkumníka serveru**, můžete získat data pro základní součást služby SharePoint, která představuje uzel. Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak získat data pro základní seznam služby SharePoint, který představuje seznam uzlů v **Průzkumníka serveru**. Ve výchozím nastavení, seznam uzlů má **zobrazit v prohlížeči** položky kontextové nabídky, které lze klepnout a otevřít ve webovém prohlížeči. Tento příklad rozšiřuje seznam uzlů přidáním **zobrazení v sadě Visual Studio** položky kontextové nabídky, která otevře seznam přímo v sadě Visual Studio. Kód získá přístup k datům v seznamu pro uzel získat adresu URL v seznamu otevřete v sadě Visual Studio.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#10)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#10)]  
  
 Tento příklad používá k získání projektu služby SharePoint <xref:EnvDTE.DTE> objekt, který se používá k otevření seznamů v sadě Visual Studio. Další informace o projektu služby SharePoint, naleznete v části [pomocí projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
 Další informace o základní úlohy vytváření rozšíření pro uzel služby SharePoint, naleznete v části [postupy: rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   EnvDTE  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 K nasazení **Průzkumníka serveru** rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Postupy: rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)   
 [Nasazování rozšíření pro nástroje služby SharePoint v aplikaci Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  