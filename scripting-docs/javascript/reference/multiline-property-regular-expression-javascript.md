---
title: Multiline – vlastnost (regulární výraz) (JavaScript) | Microsoft Docs
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
- multiline
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- multiline property
ms.assetid: ca7b276a-1fe2-4189-ac27-f089ab3e9974
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 289cb8d8e103d8c4ac1b1ef06714105d21cba743
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791403"
---
# <a name="multiline-property-regular-expression-javascript"></a>multiline – vlastnost (regulární výraz) (JavaScript)
Vrátí logickou hodnotu udávající, stav Víceřádkový příznaku (**m**) používá s regulárním výrazem. Výchozí hodnota je **false**. Jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
rgExp.multiline  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `rgExp` argument je instance `RegExp` objektu  
  
 **Víceřádkový** vlastnost vrátí **true** Pokud je nastaven pro regulární výraz příznak víceřádkové a vrátí **false** Pokud není. **Víceřádkový** vlastnost je **true** Pokud objekt regulárního výrazu byl vytvořen s **m** příznak.  
  
 Pokud **Víceřádkový** je **false**, "^" odpovídá pozici na začátku řetězce a "$" odpovídá pozici na konci řetězce. Pokud **Víceřádkový** je **true**, "^" odpovídá pozici na začátku řetězce také jako pozici "\n" nebo "\r" a "$" odpovídá pozici na konci řetězce a pozice předcházející "\n "nebo"\r".  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje chování **Víceřádkový** vlastnost. Pokud předáte "m" v funkce vidíte níže, se slovo "při" nahrazuje slovem "a". Důvodem je, že je nastavena pomocí víceřádkovým příznak a dojde k slovo "při" na začátku řádku po znak nového řádku. Příznak Víceřádkový umožňuje vyhledávání provést Víceřádkový řetězce.  
  
```JavaScript  
function RegExpMultilineDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The man hit the ball with the bat ";  
   ss += "\nwhile the fielder caught the ball with the glove.";  
  
   // Replace "while" with "and".  
   var re = new RegExp("^while", flag);  
   var r = ss.replace(re, "and");          
  
   // Output the multiline flag and the resulting string.  
   var s = "";  
   s += "Result for multiline = " + re.multiline.toString();  
   s += ": " + r;  
  
   return(s);  
  
}  
  
sa = RegExpMultilineDemo("m");  
sb = RegExpMultilineDemo("");  
document.write (sa + "<br />" + sb);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Global – vlastnost (regulární výraz)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [IgnoreCase – vlastnost (regulární výraz)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)