---
title: "prototype – vlastnost (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Prototype
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- inheritance, objects
- Prototype property
ms.assetid: 9fc434a1-5995-4fcb-a4e8-00e7f615aaa2
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a73d213b6b17f5046eb1f4c498aeb223f942f2d8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-object-javascript"></a>prototype – vlastnost (objekt) (JavaScript)
Vrátí odkaz na prototyp třídy objektů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
objectName.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `objectName` Argument je název objektu.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Array` objektu, která vrátí hodnotu největší elementu pole, deklarovat funkci, přidejte ho do `Array.prototype`a pak jeho pomocí.  
  
```JavaScript  
function array_max( ){  
    var i, max = this[0];  
    for (i = 1; i < this.length; i++)  
    {  
    if (max < this[i])  
    max = this[i];  
    }  
    return max;  
}  
Array.prototype.max = array_max;  
var myArray = new Array(7, 1, 3, 11, 25, 9  
);  
document.write(myArray.max());  
  
// Output:  
// 25  
  
```  
  
 Všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty mají `prototype` vlastnost, která je jen pro čtení. Vlastnosti a metody mohou být přidány do prototyp, ale objekt nesmí být přiřazena různých prototypu. Uživatelem definované objekty však může přiřadit nový prototypu.  
  
 Seznamy metod a vlastností pro každý vnitřní objekt v této referenční informace k jazyku znamenat ty, které jsou součástí objektu prototypu a které nejsou.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [constructor – vlastnost (Object)](../../javascript/reference/constructor-property-object-javascript.md)