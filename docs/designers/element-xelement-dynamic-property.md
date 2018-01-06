---
title: "Element (vlastnost XElement dynamické) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
apiname: XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ec02b03188ea0fd1fa7c15ea03878bdec12890f6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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