---
title: Element (vlastnost XElement dynamické) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 14078873184e4b1068f4eed931105e2e2e29dcfc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="element-xelement-dynamic-property"></a>Element (vlastnost XElement dynamické)
Získá indexeru. používá se k načtení podřízený element instanci, která odpovídá názvu zadaný rozšířené.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
elem.Element[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Indexer typu `XElement Item(String expandedName)`. Indexer vezme rozšířené název parametru a vrátí odpovídající <xref:System.Xml.Linq.XElement>, nebo `null` Pokud neexistuje žádný element se zadaným názvem.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Element%2A> metodu <xref:System.Xml.Linq.XContainer?displayProperty=fullName> třídy.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>   
 [Dynamické vlastnosti XElement – třída](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)