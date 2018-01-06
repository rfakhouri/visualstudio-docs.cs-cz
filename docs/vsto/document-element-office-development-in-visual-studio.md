---
title: "&lt;dokument&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
ms.assetid: b4525a0e-8a03-4881-a3e2-8cc019029071
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3eeabc3d271e02b83530ffd15ff2e951defcc589
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;dokument&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `document` Element `vstov4` obor názvů ukládá informace specifické pro vlastní nastavení pro úpravy na úrovni dokumentů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<document solutionId />  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 Vyžaduje se jenom pro přizpůsobení na úrovni dokumentu. `document` Elementu je `vstov4` oboru názvů. `document` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`solutionId`|Požadováno. Identifikátor GUID sady Visual Studio Tools for Office runtime používá k jedinečné identifikaci řešení úrovni dokumentu. Tato hodnota je uložena jako vlastnost _AssemblyLocation vlastní dokumentu. Další informace najdete v tématu [přehled vlastností dokumentu vlastní](../vsto/custom-document-properties-overview.md).|  
  
 `document`nemá žádné podřízené prvky.  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `document` element v řešení Office úrovni dokumentu nasadit pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstov4:document   
  solutionId="73e" />  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  