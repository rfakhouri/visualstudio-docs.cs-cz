---
title: "Hodnota (vlastnost XAttribute dynamické) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
apiname: XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7d647e7623820c6621f6605277a695a98454fec5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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