---
title: Elementy (dynamická vlastnost XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01bca0771fb02ab8442132eaff4759fe7277ad6f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53837050"
---
# <a name="elements-xelement-dynamic-property"></a>Elementy (dynamická vlastnost XElement)

Získá se používá k načtení podřízené prvky aktuálního elementu, které odpovídají zadaným rozbalený název indexeru.

## <a name="syntax"></a>Syntaxe

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer převezme rozbalený název požadované podřízené prvky a vrátí odpovídající podřízené elementy v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.

Prvky v kolekci vrácené jsou v pořadí dokumentů XML zdroje.

Tuto vlastnost používá odloženého provedení.

## <a name="see-also"></a>Viz také:

- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Element](../designers/element-xelement-dynamic-property.md)
- [Potomci](../designers/descendants-xelement-dynamic-property.md)