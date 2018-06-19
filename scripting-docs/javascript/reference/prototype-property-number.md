---
title: prototype – vlastnost (Number) | Microsoft Docs
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
ms.assetid: d5fb87af-fc3a-4469-8dde-d31daf654f94
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dba8b8886b4fdbc48a662796863b1dfca019aec
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791277"
---
# <a name="prototype-property-number"></a>prototype – vlastnost (Number)
Vrátí odkaz na prototypu pro třídu číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
number.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `number` Argument je název číslo.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Number` objektu, který vrátí číslo (Integer) číslic, deklarovat funkci, přidejte ho do `Number.prototype`a pak jeho pomocí.  
  
```JavaScript  
function number_digits() {  
    var digits = 0;  
    var num = this;  
    while (num) >= 1) {  
        digits++;  
        num /= 10;  
    }  
    return digits;  
}  
  
Number.prototype.digits = number_digits;  
var myNumber = new Number(3456.789);  
document.write(myNumber.digits());  
// Output:  
// 4  
```  
  
 Všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty mají `prototype` vlastnost, která je jen pro čtení. Vlastnosti a metody mohou být přidány do prototyp, ale objekt nesmí být přiřazena různých prototypu. Uživatelem definované objekty však může přiřadit nový prototypu.  
  
 Seznamy metod a vlastností pro každý vnitřní objekt v této referenční informace k jazyku znamenat ty, které jsou součástí objektu prototypu a které nejsou.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]