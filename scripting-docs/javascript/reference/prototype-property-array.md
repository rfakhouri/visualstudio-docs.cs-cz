---
title: prototype – vlastnost (pole) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5fedf632-8316-4e5d-ab20-10e41aa4d9f8
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fd5102fe2f49218de76c498a11256a6ef24ff0f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791211"
---
# <a name="prototype-property-array"></a>prototype – vlastnost (Pole)
Vrátí odkaz na prototypu pro třídu pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `array` Argument je název pole.  
  
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
  
// Output: 25  
```  
  
 Všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty mají `prototype` vlastnost, která je jen pro čtení. Vlastnosti a metody mohou být přidány do prototyp, ale objekt nesmí být přiřazena různých prototypu. Uživatelem definované objekty však může přiřadit nový prototypu.  
  
 Seznamy metod a vlastností pro každý vnitřní objekt v této referenční informace k jazyku znamenat ty, které jsou součástí objektu prototypu a které nejsou.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]