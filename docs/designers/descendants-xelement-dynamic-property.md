---
title: Descendants (dynamická vlastnost XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 67b82b4c5e8e34efa3dcdc98662a2428cbdfa21c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53826650"
---
# <a name="descendants-xelement-dynamic-property"></a>Descendants (dynamická vlastnost XElement)

Získá se používá k načtení všech podřízených prvků aktuálního elementu, které odpovídají zadaným rozbalený název indexeru.

## <a name="syntax"></a>Syntaxe

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer rozbalený název zadaného následnickým elementům převezme a vrátí odpovídající podřízené elementy v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.

Prvky v kolekci vrácené jsou v pořadí dokumentů XML zdroje.

Tuto vlastnost používá odloženého provedení.

## <a name="see-also"></a>Viz také:

- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Elements](../designers/elements-xelement-dynamic-property.md)