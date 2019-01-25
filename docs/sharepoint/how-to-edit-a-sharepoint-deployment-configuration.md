---
title: 'Postupy: Úprava konfigurace nasazení služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.DeploymentConfig
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 98cdc452663fd32508496c1fc52a49033a0b4381
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870058"
---
# <a name="how-to-edit-a-sharepoint-deployment-configuration"></a>Postupy: Úprava konfigurace nasazení služby SharePoint
  Můžete vytvořit konfiguraci nasazení nebo změnit existující konfiguraci nasazení. Můžete například spustit jednoho kroku nebo změnit pořadí kroků v procesu nasazení. Můžete vytvořit nebo upravit konfigurace nasazení, protože předdefinovaných a programově přidané konfigurace se nedá změnit.  
  
## <a name="create-a-sharepoint-deployment-configuration"></a>Vytvoření konfigurace nasazení služby SharePoint  
  
#### <a name="to-create-a-sharepoint-deployment-configuration"></a>Chcete-li vytvořit konfigurace nasazení služby SharePoint  
  
1.  V **Průzkumníka řešení**, zvolte projektu služby SharePoint a pak na panelu nabídek zvolte **projektu**, _ProjectName_**vlastnosti**.  
  
2.  Na **SharePoint** , vyberte **nový** tlačítko.  
  
     **Přidat novou konfiguraci nasazení** zobrazí se dialogové okno.  
  
3.  V **název** textové pole, zadejte název pro konfiguraci nasazení.  
  
4.  V **dostupné kroky nasazení** podokně, vyberte kroky, které chcete přidat ke konfiguraci nasazení, zvolte (**>**) a pak zvolte **OK** tlačítko.  
  
    > [!NOTE]  
    >  Pokud jste nakonfigurovali příkaz před nasazením nebo příkaz po nasazení, tyto kroky spustit pouze v případě, že je přidáte do konfigurace přizpůsobená nasazení.  
  
## <a name="change-the-active-deployment-configuration"></a>Změna konfigurace aktivního nasazení  
  
#### <a name="to-change-the-active-deployment-configuration"></a>Chcete-li změnit konfiguraci aktivního nasazení  
  
1.  V **Průzkumníka řešení**, zvolte projektu služby SharePoint a pak na panelu nabídek zvolte **projektu** > **\<*ProjectName*> Vlastnosti**.  
  
2.  Zvolte **SharePoint** kartu.  
  
3.  V **aktivní konfiguraci nasazení** seznamu, zvolte název, který chcete použít konfiguraci nasazení.  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
