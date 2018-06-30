---
title: 'Postupy: Úprava konfigurace nasazení služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.DeploymentConfig
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9640d98522c74fb33f8845e255511a807e03961e
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120197"
---
# <a name="how-to-edit-a-sharepoint-deployment-configuration"></a>Postupy: Úprava konfigurace nasazení služby SharePoint
  Můžete vytvořit konfiguraci nasazení nebo změnit existující konfiguraci nasazení. Například můžete spustit jeden krok nebo změnit pořadí kroků v procesu nasazení. Můžete k vytvoření nebo úprava konfigurace nasazení, protože nejde změnit konfiguraci předdefinované a přidané prostřednictvím kódu programu.  
  
## <a name="create-a-sharepoint-deployment-configuration"></a>Vytvoření konfigurace nasazení služby SharePoint  
  
#### <a name="to-create-a-sharepoint-deployment-configuration"></a>Pro vytvoření konfigurace nasazení služby SharePoint  
  
1.  V **Průzkumníku řešení**, zvolte projektu služby SharePoint a potom na řádku nabídek zvolte **projektu**, * ProjectName ***vlastnosti**.  
  
2.  Na **SharePoint** , zvolte **nový** tlačítko.  
  
     **Přidat novou konfiguraci nasazení** zobrazí se dialogové okno.  
  
3.  V **název** textové pole, zadejte název pro konfiguraci nasazení.  
  
4.  V **dostupné kroky nasazení** podokně vyberte kroky, které chcete přidat do konfigurace nasazení, vyberte (**>**) tlačítko a potom vyberte **OK** tlačítko.  
  
    > [!NOTE]  
    >  Pokud jste nakonfigurovali před nasazením příkaz nebo příkaz po nasazení, tyto kroky spustit pouze v případě, že je přidáte do konfigurace přizpůsobená nasazení.  
  
## <a name="change-the-active-deployment-configuration"></a>Změna konfigurace nasazení služby active  
  
#### <a name="to-change-the-active-deployment-configuration"></a>Chcete-li změnit konfiguraci aktivní nasazení  
  
1.  V **Průzkumníku řešení**, zvolte projektu služby SharePoint a potom na řádku nabídek zvolte **projektu** > **\<*ProjectName*> Vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **aktivní konfigurace nasazení** seznam pole, klikněte na název konfigurace nasazení, který chcete použít.  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
