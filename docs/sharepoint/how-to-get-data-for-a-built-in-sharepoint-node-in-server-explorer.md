---
title: Získání dat pro předdefinovaný uzel služby SharePoint v Průzkumníku serveru
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b90582c9b8d352f95d3d5abb3bbb7fb69283b06b
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66401422"
---
# <a name="how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer"></a>Postupy: Získání dat pro předdefinovaný uzel služby SharePoint v Průzkumníku serveru
  Pro každý předdefinovaný uzel služby SharePoint v **Průzkumníka serveru**, můžete získat data pro základní součást služby SharePoint, která představuje uzel. Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak načíst data pro základní Sharepointového seznamu, který představuje seznam uzlů v **Průzkumníka serveru**. Ve výchozím nastavení, máte seznam uzlů **zobrazit v prohlížeči** položky kontextové nabídky, který můžete kliknout a otevřít ve webovém prohlížeči. Tento příklad rozšiřuje seznam uzlů tak, že přidáte **zobrazení v sadě Visual Studio** položky kontextové nabídky, která otevře seznam přímo v sadě Visual Studio. Kód přistupuje k datům seznamu pro uzel k získání adresy URL v seznamu otevřete v sadě Visual Studio.

 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#10)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#10)]

 Tento příklad používá k získání projektu služby SharePoint <xref:EnvDTE.DTE> objekt, který se používá k otevření jsou uvedeny v sadě Visual Studio. Další informace o projektu služby SharePoint, naleznete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

 Další informace o základní úlohy vytváření rozšíření pro uzel služby SharePoint, naleznete v tématu [jak: Rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje odkazy na následující sestavení:

- EnvDTE

- Microsoft.VisualStudio.SharePoint

- Microsoft.VisualStudio.SharePoint.Explorer.Extensions

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 K nasazení **Průzkumníka serveru** rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)
- [Postupy: Rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)
- [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)
- [Nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)
