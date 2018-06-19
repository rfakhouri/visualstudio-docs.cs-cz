---
title: Hodnota (vlastnost XAttribute dynamické)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 19808b10c64b469d3d9191fa2e4fc282d7696c5f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31923588"
---
# <a name="value-xattribute-dynamic-property"></a>Hodnota (vlastnost XAttribute dynamické)

Získá nebo nastaví hodnotu atributu XML.

## <a name="syntax"></a>Syntaxe

```
attrib.Value
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

A <xref:System.String> obsahujícího hodnotu tohoto atributu.

## <a name="exceptions"></a>Výjimky

|Typ výjimky|Podmínka|
|--------------------|---------------|
|<xref:System.ArgumentNullException>|Při nastavování, `value` je `null`.|

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XAttribute.Value%2A> vlastnost <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> třídy, ale tato dynamická vlastnost také podporuje oznámení o změnách.

## <a name="see-also"></a>Viz také

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [Dynamické vlastnosti třídy XAttribute](../designers/xattribute-class-dynamic-properties.md)
- [Atribut](../designers/attribute-xelement-dynamic-property.md)