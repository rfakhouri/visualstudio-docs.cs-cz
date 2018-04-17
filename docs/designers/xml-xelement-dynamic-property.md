---
title: XML (vlastnost XElement dynamické) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d1cc5b4fdb9311c8bb76040e52151fac1aa7458
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 [Dynamické vlastnosti XElement – třída](../designers/xelement-class-dynamic-properties.md)   
 [Hodnota](../designers/value-xelement-dynamic-property.md)