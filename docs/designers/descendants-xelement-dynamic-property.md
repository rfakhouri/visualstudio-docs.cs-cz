---
title: Následníky (vlastnost XElement dynamické)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 76b08f4521182c8b50f0ca5f527068d7c97bd425
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="descendants-xelement-dynamic-property"></a>Následníky (vlastnost XElement dynamické)

Získá indexeru. používá se k načtení všechny následné prvky aktuálního elementu odpovídající rozšířené zadaný název.

## <a name="syntax"></a>Syntaxe

```
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota

Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer vezme rozbalený název zadaný následnickým elementům a vrátí odpovídající podřízených elementů v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.

## <a name="remarks"></a>Poznámky

Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.

Elementy v kolekci vrácený jsou v pořadí dokumentu XML zdrojů.

Tato vlastnost využívá odložené provedení.

## <a name="see-also"></a>Viz také

- [Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)
- [Elements](../designers/elements-xelement-dynamic-property.md)