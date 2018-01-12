---
title: "&lt;customhostspecified –&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
- application manifests [Office development in Visual Studio], <customHostSpecified> element
- <customHostSpecified> element
- customHostSpecified element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 80007310f5556bcc8c67b61e7ff41953cc7c900e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  