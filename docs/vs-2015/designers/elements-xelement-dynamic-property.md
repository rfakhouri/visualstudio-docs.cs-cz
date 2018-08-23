---
title: Elementy (dynamická vlastnost XElement) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XElement.Elements
api_type:
- Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75cb7f8f6a5259151679ecee84bbeb5db336782f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666297"
---
# <a name="elements-xelement-dynamic-property"></a>Elementy (dynamická vlastnost XElement)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Elements (dynamická vlastnost XElement)](https://docs.microsoft.com/visualstudio/designers/elements-xelement-dynamic-property).  
  
Získá se používá k načtení podřízené prvky aktuálního elementu, které odpovídají zadaným rozbalený název indexeru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer převezme rozbalený název požadované podřízené prvky a vrátí odpovídající podřízené elementy v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Elements%28System.Xml.Linq.XName%29?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.  
  
 Prvky v kolekci vrácené jsou v pořadí dokumentů XML zdroje.  
  
 Tuto vlastnost používá odloženého provedení.  
  
## <a name="see-also"></a>Viz také  
 [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)   
 [– Element](../designers/element-xelement-dynamic-property.md)   
 [Descendants](../designers/descendants-xelement-dynamic-property.md)



