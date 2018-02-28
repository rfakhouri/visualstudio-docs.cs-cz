---
title: "Rozšíření balení a nasazení SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 2fa807472a0787f0f1ae4c61f074fd8bb3ad5055
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="extending-sharepoint-packaging-and-deployment"></a>Rozšíření balení a nasazení SharePoint
  Balení a postupu nasazení pro projekty SharePoint můžete rozšířit.
  
##  <a name="creating-deployment-steps"></a>Vytváření kroky nasazení  
 Při nasazení projektu služby SharePoint, [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] provede řadu kroků nasazení. Visual Studio obsahuje vestavěné kroky nasazení pro celou řadu úloh, jako je například výsuvné a přidání řešení. Můžete však také vytvořit vlastní postup nasazení.  
  
 Návod, jak vytvořit krok nasazení najdete v tématu [návod: vytvoření vlastní krok nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).  
  
##  <a name="creating-deployment-configurations"></a>Vytvoření konfigurací nasazení  
 Konfigurace nasazení je sada kroky nasazení, které se spustí pro daný projekt, ale může mít vliv na všechny položky projektu služby SharePoint. Každá konfigurace nasazení zahrnuje jednu sadu kroky, které se spustí při nasazení projektu a jiné sady, která se spustí, až odvolán projektu. [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)]obsahuje dva předdefinované konfigurace nasazení, ale můžete taky vytvořit svoje vlastní. Při vytváření konfigurace nasazení, můžete zahrnout vestavěné kroky nasazení a kroky nasazení, které vytvoříte.  
  
 Návod, jak vytvořit konfiguraci nasazení najdete v tématu [návod: vytvoření vlastní krok nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).  
  
##  <a name="run-code-when-a-sharepoint-solution-is-deployed-or-retracted"></a>Spuštění kódu pokud je SharePoint řešení je nasazen nebo stažen  
 Může zpracovávat události k provedení dalších úloh, když je řešení služby SharePoint nasazen nebo stažen. Visual Studio vyvolává události, které může zpracovat v následujících scénářích:  
  
-   Před a po každé nasazení je krok provést pro položky projektu služby SharePoint. Další informace najdete v tématu [postupy: spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md).  
  
-   Před a po je projekt SharePoint nasazen nebo stažen. Další informace najdete v tématu [postupy: spuštění kódu pokud je projekt SharePoint nasazen nebo stažen](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md).  
  
##  <a name="handling-deployment-conflicts"></a>Zpracování konfliktů nasazení  
 Některé typy položek projektu služby SharePoint, včetně modulů, webové části, seznam instancí a typy obsahu, zadejte předdefinované nasazení řešení konfliktů. Při nasazení řešení, které obsahuje jeden z těchto položek projektu sady Visual Studio, nejprve ověří, zda soubor již existuje na webu služby SharePoint se stejným názvem, adresa URL nebo ID jako soubor v položku, kterou nasazujete. Pokud existuje konflikt, Visual Studio můžete automaticky vyřešit konflikt nebo můžete vyzvat, je možné určit, zda chcete mít Visual Studio konflikt vyřešit nebo zrušení nasazení. Další informace najdete v tématu [řešení potíží s balení a nasazení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
 Tuto funkci můžete rozšířit o vlastní kód, který kontroluje a řeší konflikty nasazení. Další informace najdete v tématu [postupy: zpracování konfliktů nasazení](../sharepoint/how-to-handle-deployment-conflicts.md).  
  
##  <a name="run-command-line-operations-before-or-after-a-project-is-deployed"></a>Spusťte příkazový řádek Operations před nebo po projektu nasazení  
 Pokud chcete spouštět operace příkazového řádku při nasazení řešení služby SharePoint, můžete nastavit <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PreDeploymentCommand%2A> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PostDeploymentCommand%2A> vlastnosti <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu. Visual Studio provede tyto příkazy před a po nasazení projektu.  
  
 V některých případech se může zobrazit konflikty nasazení. Řešení konfliktů několika různými způsoby. Další informace najdete v tématu [řešení potíží s balení a nasazení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
##  <a name="customizing-validation-rules"></a>Přizpůsobení ověřovacích pravidel  
 Před nasazením balíčku řešení (WSP), můžete vytvořit vlastní funkce a balíku ověřovací pravidla pro ověření, že funkce nebo balíčku je platný. Například může hlásit informace, varování nebo chyby vývojáři k jejich vyřešení potíží ověřování. Další informace najdete v tématu [postupy: vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)   
 [Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [Postupy: vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)   
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  
