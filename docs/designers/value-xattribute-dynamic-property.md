---
title: Hodnota (vlastnost XAttribute dynamické) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0ca01f5d7aec5807343b98a3c402a89678fbe88
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>   
 [Dynamické vlastnosti XAttribute – třída](../designers/xattribute-class-dynamic-properties.md)   
 [Atribut](../designers/attribute-xelement-dynamic-property.md)