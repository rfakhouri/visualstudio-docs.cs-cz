---
title: '&lt;friendlyName&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <friendlyName> element
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: bcb22c14931992f572f7ffbb4ea74bec852714d0
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648455"
---
# <a name="ltfriendlynamegt-element-office-development-in-visual-studio"></a>&lt;friendlyName&gt; – element (vývoj pro Office v sadě Visual Studio)
  `friendlyName` Elementu `vstov4` obor názvů obsahuje název, který se zobrazí v seznamu nainstalovaných programů.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml
<friendlyName>  
</friendlyName>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `friendlyName` Elementu je `vstov4` oboru názvů. Hodnota se zobrazí v seznamu nainstalovaných programů v počítači a v dialogovém okně doplňků VSTO modelu COM z aplikace Microsoft Office.  
  
 `friendlyName` Prvek nemá žádné atributy a podřízené prvky.  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje, `friendlyName` prvek v řešení úrovni aplikace nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```xml  
<vstov4:friendlyName>  
  ContosoOutlookAddIn  
</vstov4:friendlyName>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)  
  