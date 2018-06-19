---
title: 0... n vlastnosti (arguments) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- 0...n
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- 0...n properties
ms.assetid: 52857c4b-3d56-4500-93ff-4db4729c2578
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f46c7dafef1cdc27d27f619936349637af172740
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789078"
---
# <a name="0n-properties-arguments-javascript"></a>0...n – vlastnosti (arguments) (JavaScript)
Vrací aktuální hodnotu jednotlivých argumentů z **argumenty** objekt vrácený **argumenty** vlastnost provádění funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[function.]arguments[[0|1|2|...|n]]  
```  
  
## <a name="parameters"></a>Parametry  
 *funkce*  
 Volitelné. Název aktuálně spuštěných `Function` objektu.  
  
 0, 1, 2, *, n*  
 Požadováno. Nezáporné celé číslo v rozsahu od 0 do  *n*  kde 0 představuje první argument a  *n*  představuje konečný argument. Hodnota argumentu konečné  *n*  je **arguments.length-1**.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty vrácené funkcí 0. . . n vlastnosti jsou skutečnými hodnotami provádění funkci byl předán. Při ve skutečnosti není pole argumentů, jednotlivé argumenty, které tvoří **argumenty** objekt přistupuje stejným způsobem, že jsou přístupné prvků pole.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **0...**  ***n***vlastnosti **argumenty** objektu. Abyste plně porozuměli tomu v příkladu, předejte některé argumenty funkce:  
  
```JavaScript  
function ArgTest(){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello", new Date()));  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [objekt arguments](../../javascript/reference/arguments-object-javascript.md)&#124; [Funkce objektu](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Length – vlastnost (arguments)](../../javascript/reference/length-property-arguments-javascript.md)   
 [Length – vlastnost (Function)](../../javascript/reference/length-property-function-javascript.md)