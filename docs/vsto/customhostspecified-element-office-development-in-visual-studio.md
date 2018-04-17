---
title: '&lt;customhostspecified –&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <customHostSpecified> element
- <customHostSpecified> element
- customHostSpecified element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9d74dac27e4d4a5735dc73ebb069d985d17022d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltcustomhostspecifiedgt-element-office-development-in-visual-studio"></a>&lt;customhostspecified –&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `customHostSpecified` Element signalizuje, že toto řešení není samostatné aplikace. Řešení Office obsahovat součásti, které jsou hostované v rámci aplikace Microsoft Office.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<customHostSpecified />  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `customHostSpecified` Prvek je nutný pro řešení Office. Tento element má `co.v1` obor názvů a určuje, že toto nasazení obsahuje součást, která bude nasazena uvnitř vlastního hostitele a není samostatné aplikace.  
  
 Tento element je podřízená první `<entrypoint>` element v manifestu aplikace. Může být žádné další podřízené prvky v tom, že `<entrypoint>` element nebo [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] dosáhne chyby ověření během instalace.  
  
 Tento element má žádné atributy a žádné podřízené prvky.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `customHostSpecified` element v manifestu aplikace pro řešení Office. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  