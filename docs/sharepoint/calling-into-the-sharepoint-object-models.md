---
title: "Volání do služby SharePoint objektové modely | Microsoft Docs"
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
- SharePoint development in Visual Studio, client object model
- SharePoint development in Visual Studio, server object model
- SharePoint commands [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, extensibility features
ms.assetid: 99934f9e-901e-464e-ac8c-22c6c86440f4
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b1a0f4175dc884283dcf92b7f6268a518cdaf0ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="calling-into-the-sharepoint-object-models"></a>Volání do objektových modelů služby SharePoint
  Při vytváření rozšíření pro nástroje služby SharePoint v sadě Visual Studio, bude pravděpodobně k volání rozhraní API služby SharePoint k provedení určité úlohy. Například pokud vytvoříte vlastního kroku nasazení pro projekty SharePoint, budete možná muset volání rozhraní API služby SharePoint k provedení některých úkolů k nasazení řešení.  
  
 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]a [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] zadejte dva různé objektové modely, které můžete použít v rozšíření nástrojů služby SharePoint: objektový model serveru a objektového modelu klienta. Každý objektový model má své výhody a nevýhody v kontextu rozšíření nástrojů služby SharePoint.  
  
 Přehled objektových modelů služby SharePoint, naleznete v části [přehled programovací Model z rozšíření nástrojů SharePoint](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).  
  
## <a name="using-the-client-object-model-in-extension-projects"></a>Pomocí objektového modelu klienta v rozšíření projektů  
 Když budete vyvíjet rozšíření pro nástroje služby SharePoint, můžete ve vašem projektu jako jinou sadu spravovaných rozhraní API objektového modelu klienta. Odkazy na sestavení v objektového modelu klienta můžete přidat do projektu a můžete volat rozhraní API v objektového modelu klienta přímo z vašeho kódu.  
  
 Objektového modelu klienta však má dva nevýhody v kontextu rozšíření nástrojů služby SharePoint:  
  
-   Objektový model klienta obsahuje pouze podmnožinu objektový model serveru. Pokud máte používat funkce služby SharePoint, který není vystavený v objektového modelu klienta, musíte použít objektový model serveru.  
  
-   I když v rozšíření nástrojů služby SharePoint pomocí objektového modelu klienta by mělo fungovat ve většině případů můžete setkat některých scénářích, kde volání objektového modelu klienta nefungují podle očekávání. Objektového modelu klienta je určena pro použití v klientských aplikacích pro volání do webů služby SharePoint na vzdálený server nebo farmu. Nástroje služby SharePoint v sadě Visual Studio fungovat jenom s místní instalací služby SharePoint na vývojovém počítači. Proto při použití objektového modelu klienta v rozšíření nástrojů služby SharePoint, volat na webu služby SharePoint v místním počítači, který je, jak objektového modelu klienta nebyl určen k použití.  
  
 Návod, jak pomocí objektového modelu klienta v rozšíření nástrojů služby SharePoint v sadě Visual Studio najdete v tématu [návod: volání do modelu klientského objektu služby SharePoint v rozšíření Průzkumníka serveru](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## <a name="using-the-server-object-model-in-extension-projects"></a>Použití objektový Model serveru v rozšíření projektů  
 Objektový model serveru je nadmnožinou objektového modelu klienta. Použijete-li objektový model serveru, můžete použít všechny funkce, [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] a [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] zpřístupnit prostřednictvím kódu programu.  
  
 Rozšíření nástrojů služby SharePoint můžete použít rozhraní API v objektovém modelu serveru, ale nemohou přímo volat rozhraní API. Objektový model serveru lze volat pouze z 64bitového procesu s cílem rozhraní .NET Framework 3.5. Ale rozšíření nástrojů SharePoint vyžaduje [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a spouští se v procesu 32bitová verze sady Visual Studio. Rozšíření nástrojů SharePoint zabrání odkazování na sestavení v objektovém modelu serveru SharePoint přímo.  
  
 Pokud chcete použít objektový model serveru v rozšíření nástrojů služby SharePoint, je třeba vytvořit vlastní *příkazu SharePoint* pro volání rozhraní API. Příkaz SharePoint definujete v sekundárním sestavení, které můžete volat přímo do objektový model serveru. V projektu rozšíření můžete volání příkazu SharePoint nepřímo metodě ExecuteCommand <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> objektu.  
  
 Další informace o vytváření a použití příkazů služby SharePoint, naleznete v části [postupy: vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md) a [postup: provedení příkazu SharePoint](../sharepoint/how-to-execute-a-sharepoint-command.md). Informace o tom, jak nasadit SharePoint – příkazy najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
 Návody, které ukazují, jak vytvořit a použít příkazy služby SharePoint, naleznete v části [návod: vytvoření vlastní krok nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md) a [návod: rozšíření Průzkumníka serveru pro webové zobrazení Části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
### <a name="understanding-how-sharepoint-commands-are-executed"></a>Provedení pochopení jak SharePoint – příkazy  
 Sestavení, které definují příkazy služby SharePoint jsou načteny v procesu 64-bit hostitele s názvem vssphost4.exe. Po zavolání metody příkazu SharePoint v rozšíření nástrojů služby SharePoint, je spustit příkaz vssphost4.exe místo proces 32bitová verze sady Visual Studio (devenv.exe). Můžete ovládat některé aspekty jak jsou provedeny příkazy SharePoint nastavením hodnoty v registru. Další informace najdete v tématu [ladění rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření příkazu SharePoint](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [Postup: provedení příkazu SharePoint](../sharepoint/how-to-execute-a-sharepoint-command.md)   
 [Přehled modelu programování rozšíření nástrojů služby SharePoint](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  