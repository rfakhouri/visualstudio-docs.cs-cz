---
title: Atribut (dynamická vlastnost XElement)
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ec27fe2d7824ca32cbf97dbabac8b7ea6c4aed6
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55948495"
---
# <a name="attribute-xelement-dynamic-property"></a>Atribut (dynamická vlastnost XElement)

Získá se používá k načtení instance atributu, který odpovídá zadané rozbalený název indexeru.

## <a name="syntax"></a>Syntaxe

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

Indexer typu `XAttribute Item(String expandedName)`. Indexer vezme rozbalený název zadaného atributu a vrátí odpovídající <xref:System.Xml.Linq.XAttribute>, nebo `null` Pokud neexistuje žádný atribut se zadaným názvem.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XElement.Attribute%2A> metodu <xref:System.Xml.Linq.XElement?displayProperty=fullName> třídy.

## <a name="see-also"></a>Viz také:

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Hodnota](../designers/value-xattribute-dynamic-property.md)