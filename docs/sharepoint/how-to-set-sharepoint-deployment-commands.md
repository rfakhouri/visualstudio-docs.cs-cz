---
title: 'Postupy: Nastavení příkazů nasazení služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
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
ms.openlocfilehash: e76a1e4e19f8f3280b6da71dffa19d3a7e2c16a5
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54871776"
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>Postupy: Nastavení příkazů nasazení služby SharePoint
  Proces nasazení můžete přizpůsobit tak, že nastavíte příkazy před nasazením a po nasazení. Tyto příkazy se spouští před a po další akce související s nasazením při ladění řešení služby SharePoint v sadě Visual Studio.  
  
### <a name="to-add-a-pre-deployment-command"></a>Chcete-li přidat příkaz před nasazením  
  
1.  V panelu nabídky zvolte **projektu** > **\<*ProjectName*> vlastnosti**.  
  
2.  Zvolte **SharePoint** kartu.  
  
3.  V **příkazový řádek před nasazením** textové pole, zadejte zástupného kódu MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     K výpisu obsahu adresáře předtím, než se dokončí nasazení, zadejte například **dir**.  
  
### <a name="to-add-a-post-deployment-command"></a>Chcete-li přidat příkaz po nasazení  
  
1.  V panelu nabídky zvolte **projektu** > **\<*ProjectName*> vlastnosti**.  
  
2.  Zvolte **SharePoint** kartu.  
  
3.  V **příkazový řádek po nasazení** textové pole, zadejte zástupného kódu MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     K výpisu obsahu adresáře po dokončení nasazení, zadejte například **dir**. Použití nástroje MSBuild proměnné ke zkopírování sestavení z adresáře sestavení, zadejte **zkopírujte $(TargetPath) c:\DeploymentDirectory**.  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
