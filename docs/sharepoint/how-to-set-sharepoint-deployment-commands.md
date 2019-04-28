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
ms.openlocfilehash: 7664dfcfe11d7ab7dc6ab03045533bbd9e69fb9c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812907"
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>Postupy: Nastavení příkazů nasazení služby SharePoint
  Proces nasazení můžete přizpůsobit tak, že nastavíte příkazy před nasazením a po nasazení. Tyto příkazy se spouští před a po další akce související s nasazením při ladění řešení služby SharePoint v sadě Visual Studio.

### <a name="to-add-a-pre-deployment-command"></a>Chcete-li přidat příkaz před nasazením

1. V panelu nabídky zvolte **projektu** > **\<*ProjectName*> vlastnosti**.

2. Zvolte **SharePoint** kartu.

3. V **příkazový řádek před nasazením** textové pole, zadejte zástupného kódu MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.

     K výpisu obsahu adresáře předtím, než se dokončí nasazení, zadejte například **dir**.

### <a name="to-add-a-post-deployment-command"></a>Chcete-li přidat příkaz po nasazení

1. V panelu nabídky zvolte **projektu** > **\<*ProjectName*> vlastnosti**.

2. Zvolte **SharePoint** kartu.

3. V **příkazový řádek po nasazení** textové pole, zadejte zástupného kódu MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.

     K výpisu obsahu adresáře po dokončení nasazení, zadejte například **dir**. Použití nástroje MSBuild proměnné ke zkopírování sestavení z adresáře sestavení, zadejte **zkopírujte $(TargetPath) c:\DeploymentDirectory**.

## <a name="see-also"></a>Viz také:
- [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
