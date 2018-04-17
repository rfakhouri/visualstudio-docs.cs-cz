---
title: '&lt;Popis&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- description element
- <description> element
- application manifests [Office development in Visual Studio], <description> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 13755a20b091696bf741c1f25360941e01b65945
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltdescriptiongt-element-office-development-in-visual-studio"></a>&lt;Popis&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `description` Element `vstov4` obor názvů ukládá popis řešení Office, který se zobrazí v dialogovém okně Doplňky COM z aplikace Microsoft Office.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<description>  
</description>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 Volitelné. `description` Elementu je `vstov4` oboru názvů. Obsahuje popis doplněk, který se zobrazí v dialogovém okně Doplňky COM z aplikace Microsoft Office.  
  
 `description` Element nemá žádné atributy nebo elementy.  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `description` element pro řešení s úrovni aplikace nasazené pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstov4:description>  
  ContosoOutlookAddIn - Outlook add-in   
  created with Visual Studio Tools for Office  
</vstov4:description>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  