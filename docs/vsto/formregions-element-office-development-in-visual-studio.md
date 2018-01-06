---
title: "&lt;formregions –&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
- formRegions element
- <formRegions> element
- application manifests [Office development in Visual Studio], <formRegions> element
ms.assetid: 71faa2da-9d38-43e8-9d7d-0bcd944ef9a3
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f8ec444f9dade9fc0053680ed242e94cc5543bdf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltformregionsgt-element-office-development-in-visual-studio"></a>&lt;formregions –&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `formRegions` Element `vstov4` obor názvů obsahuje oblastí formulářů aplikace Microsoft Office Outlook, které jsou spojeny s doplňku VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<formRegions>  
  <formRegion>  
  </formRegion>  
</formRegions>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `formRegions` Element `vstov4` obor názvů obsahuje všechny `formRegion` prvky pro doplňku VSTO v Outlooku. Je vyžadována pouze pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.  
  
 Může být jen jedna `formRegions` element definovaný v manifestu aplikace.  
  
 `formRegions` Element nemá žádné atributy.  
  
 `formRegions` Element má následující element.  
  
### <a name="formregion"></a>formRegion  
 Vyžaduje se pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů. `formRegion` Element je definována v [& č. 60; formRegion & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/formregion-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `formRegions` element v manifestu aplikace pro řešení Office úrovni aplikace nasazené pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstov4:formRegions>  
  <vstov4:formRegion  
      name="OutlookAddIn1.FormRegion1">  
    <vstov4:messageClass name="IPM.Note" />  
    <vstov4:messageClass name="IPM.Contact" />  
    <vstov4:messageClass name="IPM.Appointment" />  
  </vstov4:formRegion>  
</vstov4:formRegions>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  