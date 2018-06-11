---
title: Manifesty aplikace a nasazení v řešeních pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- manifests [Office development in Visual Studio]
- deployment manifests [Office development in Visual Studio]
- application manifests [Office development in Visual Studio]
- assemblies [Office development in Visual Studio], updating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f3fba49e90bbe0f5350a5d778b8591ec473807be
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257999"
---
# <a name="application-and-deployment-manifests-in-office-solutions"></a>Manifesty aplikace a nasazení v řešeních pro systém Office
  Manifest aplikace je soubor XML, který poskytuje informace, který je používán řešení Office pro vyhledání a aktualizujte jeho sestavení. Manifest aplikace můžete použít s manifestu nasazení, který je soubor XML, který je uložený na serveru, který poskytuje informace potřebné k vyhledání nejaktuálnější verzi manifest aplikace a sestavení.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="manifest-structure-for-office-solutions"></a>Manifest strukturu pro řešení pro systém Office  
 Pro aplikace Microsoft Office řešení vytvořená pomocí nástrojů pro vývoj pro Office v sadě Visual Studio jsou všechny manifesty založené na standardní ClickOnce schématu. Při nasazení řešení Office manifesty aplikace pro úrovni dokumentu a projekty doplňku VSTO se nachází v mezipaměti ClickOnce. Manifesty nasazení nebudou zkopírovány do klientského počítače.  
  
 Informace o obsahu manifestů aplikace a nasazení pro projekty Office, najdete v části [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md) a [manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md).  
  
## <a name="create-application-and-deployment-manifests"></a>Vytvoření manifestů aplikace a nasazení  
 Manifesty aplikace se vytvoří automaticky v rámci procesu sestavení. Pokaždé, když vytvoříte projekt na úrovni dokumentu a, umístění manifestu nasazení je vložen do dokumentu jako vlastnost vlastní dokumentu. Umístění manifestu nasazení je pro doplňky VSTO uložené v registru.  
  
 Další informace o **Průvodci publikováním**, najdete v části [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
 Další informace o manifesty pracují s řešení pro systém Office, najdete v části [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také:  
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)   
 [ClickOnce – manifest nasazení](/visualstudio/deployment/clickonce-deployment-manifest)  
  
  