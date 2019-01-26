---
title: XML (dynamická vlastnost XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0cadfd6f02cbe431cb5a74db4a3b7008d05d9c05
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55026980"
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