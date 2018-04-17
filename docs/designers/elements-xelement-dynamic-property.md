---
title: Elementy (vlastnost XElement dynamické) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7c68611dc8377d9fc32f6eedbbfd0114959cf08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="elements-xelement-dynamic-property"></a>Elementy (vlastnost XElement dynamické)
Získá indexeru. používá se k načtení podřízených elementů aktuálního elementu, které odpovídají zadaným názvem rozšířené.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer vezme rozbalený název požadované podřízené elementy a vrátí odpovídající podřízených elementů v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.  
  
 Elementy v kolekci vrácený jsou v pořadí dokumentu XML zdrojů.  
  
 Tato vlastnost využívá odložené provedení.  
  
## <a name="see-also"></a>Viz také  
 [Dynamické vlastnosti XElement – třída](../designers/xelement-class-dynamic-properties.md)   
 [Element](../designers/element-xelement-dynamic-property.md)   
 [Následníky](../designers/descendants-xelement-dynamic-property.md)