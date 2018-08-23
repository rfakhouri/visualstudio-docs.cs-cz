---
title: Descendants (dynamická vlastnost XElement) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 29f73bb664e9664ac2a3c56942c86949c9e2bba2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633584"
---
# <a name="descendants-xelement-dynamic-property"></a>Descendants (dynamická vlastnost XElement)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Descendants (dynamická vlastnost XElement)](https://docs.microsoft.com/visualstudio/designers/descendants-xelement-dynamic-property).  
  
Získá se používá k načtení všech podřízených prvků aktuálního elementu, které odpovídají zadaným rozbalený název indexeru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
elem.Descendants[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer rozbalený název zadaného následnickým elementům převezme a vrátí odpovídající podřízené elementy v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Descendants%28System.Xml.Linq.XName%29?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.  
  
 Prvky v kolekci vrácené jsou v pořadí dokumentů XML zdroje.  
  
 Tuto vlastnost používá odloženého provedení.  
  
## <a name="see-also"></a>Viz také  
 [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)



