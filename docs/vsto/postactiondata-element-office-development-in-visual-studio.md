---
title: '&lt;postactiondata –&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <postActionData> element
- application manifests [Office development in Visual Studio], <postActionData> element
- postActionData element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c33e2bae7214252f0d0a871ed5a21a62d3fb9372
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltpostactiondatagt-element-office-development-in-visual-studio"></a>&lt;postactiondata –&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `postActionData` Element `vstav3` data související s jakoukoliv akci po nasazení, která spustí po instalaci řešení pro systém Office Určuje obor názvů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<postActionData>  
</postActionData>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `postActionData` Element je volitelný a je v `vstav3` oboru názvů. Existuje `postActionData` element definovaný v manifest aplikace pro každou akci po nasazení.  
  
 `postActions` Element nemá žádné atributy.  
  
 `postActions` nemá žádné podřízené prvky.  
  
## <a name="post-deployment-action-example"></a>Příklad akce po nasazení  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `postAction` element v manifestu aplikace pro řešení Office nasadit pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:postActionData>  
  data in any format  
</vstav3:postActionData>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  