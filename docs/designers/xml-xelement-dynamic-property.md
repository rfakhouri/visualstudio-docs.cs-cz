---
title: XML (vlastnost XElement dynamické)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36b2100218267587e2ea5d38ad62f7ed28dbc102
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="xml-xelement-dynamic-property"></a>XML (vlastnost XElement dynamické)

Získá neformátovaný XML obsahu elementu.

## <a name="syntax"></a>Syntaxe

```
elem.Xml
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

A <xref:System.String> představující neformátovaný obsah XML elementu.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> metodu <xref:System.Xml.Linq.XNode?displayProperty=fullName> třídy, se `SaveOptions` parametr nastaven na <xref:System.Xml.Linq.SaveOptions>.

## <a name="see-also"></a>Viz také

- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Hodnota](../designers/value-xelement-dynamic-property.md)