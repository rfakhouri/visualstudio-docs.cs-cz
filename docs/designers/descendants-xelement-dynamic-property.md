---
title: Následníky (vlastnost XElement dynamické) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8520ae91e2a4983e2cc8bcf0e04562255bf4fc1d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 [Dynamické vlastnosti XElement – třída](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)