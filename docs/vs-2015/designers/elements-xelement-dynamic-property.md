---
title: Elementy (dynamická vlastnost XElement) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
api_name:
- XElement.Elements
api_type:
- Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 158e200a33b4783df9f63f42a1eca7bb8957d449
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54777698"
---
# <a name="elements-xelement-dynamic-property"></a>Elementy (dynamická vlastnost XElement)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
 [Potomci](../designers/descendants-xelement-dynamic-property.md)
