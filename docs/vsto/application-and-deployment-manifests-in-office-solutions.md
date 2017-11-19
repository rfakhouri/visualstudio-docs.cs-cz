---
title: "Aplikace a nasazení manifesty v řešeních pro systém Office | Microsoft Docs"
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
- manifests [Office development in Visual Studio]
- deployment manifests [Office development in Visual Studio]
- application manifests [Office development in Visual Studio]
- assemblies [Office development in Visual Studio], updating
ms.assetid: 4e9abc7c-ef9f-4cb2-a7a9-c95c5f4a1fb7
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 822be7f0e6e79f600331197c60ed48ea84cde200
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="application-and-deployment-manifests-in-office-solutions"></a>Manifesty aplikací a nasazení v řešeních pro systém Office
  Manifest aplikace je soubor XML, který poskytuje informace, který je používán řešení Office pro vyhledání a aktualizujte jeho sestavení. Manifest aplikace můžete použít s manifestu nasazení, který je soubor XML, který je uložený na serveru, který poskytuje informace potřebné k vyhledání nejaktuálnější verzi manifest aplikace a sestavení.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="manifest-structure-for-office-solutions"></a>Manifestu strukturu pro řešení pro systém Office  
 Pro aplikace Microsoft Office řešení vytvořená pomocí nástrojů pro vývoj pro Office v sadě Visual Studio jsou všechny manifesty založené na standardní ClickOnce schématu. Při nasazení řešení Office manifesty aplikace pro úrovni dokumentu a projekty doplňku VSTO se nachází v mezipaměti ClickOnce. Manifesty nasazení nebudou zkopírovány do klientského počítače.  
  
 Informace o obsahu manifestů aplikace a nasazení pro projekty Office, najdete v části [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md) a [manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md).  
  
## <a name="creating-application-and-deployment-manifests"></a>Vytváření aplikací a nasazení manifesty  
 Manifesty aplikace se vytvoří automaticky v rámci procesu sestavení. Pokaždé, když vytvoříte projekt na úrovni dokumentu a, umístění manifestu nasazení je vložen do dokumentu jako vlastnost vlastní dokumentu. Umístění manifestu nasazení je pro doplňky VSTO uložené v registru.  
  
 Další informace o **Průvodci publikováním**, najdete v části [nasazení řešení Office aplikací ClickOnce pomocí](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
 Další informace o manifesty pracují s řešení pro systém Office, najdete v části [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – Manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)   
 [ClickOnce – Manifest nasazení](/visualstudio/deployment/clickonce-deployment-manifest)  
  
  