---
title: "Postupy: získání dat pro předdefinovaný uzel služby SharePoint v Průzkumníku serveru | Microsoft Docs"
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
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
ms.assetid: 86d04e0a-c114-427e-9945-da5fa339fda4
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: fa518bf566671dda2b54489fa37460840365bc70
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  