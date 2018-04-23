---
title: Atribut (vlastnost XElement dynamické)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9378a7649a3e99a0327586ab2e9f7234b66615f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="attribute-xelement-dynamic-property"></a>Atribut (vlastnost XElement dynamické)

Získá indexeru. používá se k načtení atribut instanci, která odpovídá názvu zadaný rozšířené.

## <a name="syntax"></a>Syntaxe

```
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

Indexer typu `XAttribute Item(String expandedName)`. Indexer vezme rozbalený název zadaného atributu a vrátí odpovídající <xref:System.Xml.Linq.XAttribute>, nebo `null` Pokud atribut neexistuje se zadaným názvem.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XElement.Attribute%2A> metodu <xref:System.Xml.Linq.XElement?displayProperty=fullName> třídy.

## <a name="see-also"></a>Viz také

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Hodnota](../designers/value-xattribute-dynamic-property.md)