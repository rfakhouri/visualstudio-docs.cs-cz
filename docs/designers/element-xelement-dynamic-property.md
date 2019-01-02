---
title: – Element (dynamická vlastnost XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e292be4458459fff2a3784d989e603f21dcb53c9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53888059"
---
# <a name="element-xelement-dynamic-property"></a>– Element (dynamická vlastnost XElement)

Získá indexeru se používá k načtení podřízený element instanci, která odpovídá zadaným rozbalený název.

## <a name="syntax"></a>Syntaxe

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

Indexer typu `XElement Item(String expandedName)`. Indexer přijímá parametr rozbalený název a vrátí odpovídající <xref:System.Xml.Linq.XElement>, nebo `null` Pokud neexistuje žádný element se zadaným názvem.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní k <xref:System.Xml.Linq.XContainer.Element%2A> metodu <xref:System.Xml.Linq.XContainer?displayProperty=fullName> třídy.

## <a name="see-also"></a>Viz také:

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Elements](../designers/elements-xelement-dynamic-property.md)