---
title: Hodnota (dynamická vlastnost XAttribute)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e5ab4711d0165511aaf5934eeab1a81308fc3084
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031117"
---
# <a name="value-xattribute-dynamic-property"></a>Hodnota (dynamická vlastnost XAttribute)

Získá nebo nastaví hodnotu atributu XML.

## <a name="syntax"></a>Syntaxe

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>Vlastnost hodnota nebo návratová hodnota

A <xref:System.String> obsahující hodnotu tohoto atributu.

## <a name="exceptions"></a>Výjimky

|Typ výjimky|Podmínka|
| - |---------------|
|<xref:System.ArgumentNullException>|Při nastavování, `value` je `null`.|

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XAttribute.Value%2A> vlastnost <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> třídy, ale tato dynamická vlastnost také podporuje oznámení o změnách.

## <a name="see-also"></a>Viz také:

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [Dynamické vlastnosti třídy XAttribute](../designers/xattribute-class-dynamic-properties.md)
- [Atribut](../designers/attribute-xelement-dynamic-property.md)