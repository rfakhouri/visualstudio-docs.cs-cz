---
title: XML (dynamická vlastnost XElement)
ms.date: 11/04/2016
ms.topic: reference
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7d58dea02a45ccc84e7829da2acdb479eb17dda3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55931244"
---
# <a name="xml-xelement-dynamic-property"></a>Xml (dynamická vlastnost XElement)

Získá neformátovaném tvaru XML obsahu elementu.

## <a name="syntax"></a>Syntaxe

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a>Vlastnost hodnota nebo návratová hodnota

A <xref:System.String> , která představuje neformátovaný obsah XML daného elementu.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní k <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> metodu <xref:System.Xml.Linq.XNode?displayProperty=fullName> třídy, se `SaveOptions` parametr nastaven na <xref:System.Xml.Linq.SaveOptions>.

## <a name="see-also"></a>Viz také:

- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Hodnota](../designers/value-xelement-dynamic-property.md)