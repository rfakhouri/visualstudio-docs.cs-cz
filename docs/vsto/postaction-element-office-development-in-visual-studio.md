---
title: "&lt;postAction&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
- application manifests [Office development in Visual Studio], <postAction> element
- <postAction> element
- postAction element
ms.assetid: a047e2e2-9732-4140-b8bd-bc5bd1b84291
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 581ef7bafc075419df8e2dfb1731b334a9564455
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ltpostactiongt-element-office-development-in-visual-studio"></a>&lt;postAction&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `postAction` Element `vstav3` obor názvů obsahuje `entrypoint` elementy a všechny `postActionData` prvky, které jsou spojeny s akcemi po nasazení, které se spustit po instalaci řešení pro systém Office.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<postAction>  
  <entryPoint>  
  </entryPoint>  
  <postActionData>  
  </postActionData>  
</postAction>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `postAction` Prvek je volitelný a je v `vstav3` oboru názvů. Existuje `postAction` element definovaný v manifest aplikace pro každou akci po nasazení.  
  
 `postAction` Element nemá žádné atributy.  
  
 `postAction`obsahuje následující prvky.  
  
### <a name="entrypoint"></a>Vstupní bod  
 Volitelné. Role `entryPoint` element v `vstav3` obor názvů je definován v [& č. 60; entryPoints & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/entrypoints-element-office-development-in-visual-studio.md).  
  
### <a name="postactiondata"></a>postactiondata –  
 Volitelné. Role `postActionData` element v `vstav3` obor názvů je definován v [& č. 60; postactiondata – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/postactiondata-element-office-development-in-visual-studio.md).  
  
## <a name="post-deployment-action-example"></a>Příklad akce po nasazení  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `postAction` element v manifestu aplikace, pro které je nasazeno pomocí řešení Office [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:postAction>  
  <vstav3:entryPoint   
    class="PostDeploymentAction.PostDeploymentActionSample">  
    <assemblyIdentity   
      name="PostDeploymentAction"   
      version="1.0.0.0"   
      language="neutral"   
      processorArchitecture="msil" />  
  </vstav3:entryPoint>  
  <vstav3:postActionData>  
  </vstav3:postActionData>  
</vstav3:postAction>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – Manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)  
  
  