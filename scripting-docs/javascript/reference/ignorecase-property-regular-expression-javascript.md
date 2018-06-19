---
title: IgnoreCase – vlastnost (regulární výraz) (JavaScript) | Microsoft Docs
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
- ignoreCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- IgnoreCase property
ms.assetid: 816f0df5-5a82-44a5-a4ab-dbc91fa76e61
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae9fee8e6303fb944f59c11c173f9e8b7f7cc75a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790866"
---
# <a name="ignorecase-property-regular-expression-javascript"></a>ignoreCase – vlastnost (regulární výraz) (JavaScript)
Vrátí logickou hodnotu udávající, stav příznak ignoreCase (**i**) používá s regulárním výrazem. Výchozí hodnota je **false**. Jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
rgExp.ignoreCase  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `rgExp` odkaz je instance `RegExp` objektu.  
  
 **IgnoreCase** vlastnost vrátí **true** Pokud příznak ignoreCase je nastaven pro regulární výraz a vrátí **false** Pokud není.  
  
 Příznak ignoreCase, pokud se použije, označuje, s hledání by měl ignorovat rozlišování velkých a malých písmen při porovnávání vzoru v rámci vyhledávaná řetězce.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **ignoreCase** vlastnost. Pokud předáte "grafického rozhraní" v následující funkce, všechny instance aplikace word "na" jsou nahrazena slovem "a", včetně počáteční "Na". To je proto ignoreCase příznak nastaven, hledání ignoruje všechny malá a velká písmena. Proto "T" je stejný jako "t" pro účely porovnávání.  
  
 Tato funkce vrátí logické hodnoty, které označují stav povolená regulární výraz příznaky, které jsou **g**, **i**, a **m**. Funkce také vrátí řetězec s všechny nahrazené provedeny.  
  
```JavaScript  
function RegExpPropDemo(flag){  
    // The flag parameter is a string that contains  
    // g, i, or m. The flags can be combined.  
  
    // Check flags for validity.  
    if (flag.match(/[^gim]/))  
        {  
        return ("Flag specified is not valid");  
        }  
  
    // Create the string on which to perform the replacement.  
    var orig = "The batter hit the ball with the bat ";  
    orig += "and the fielder caught the ball with the glove.";  
  
    // Replace "the" with "a".  
    var re = new RegExp("the", flag);  
    var r = orig.replace(re, "a");          
  
    // Output the resulting string and the values of the flags.  
    var s = "";  
    s += "global: " + re.global.toString();  
    s += "<br />";  
    s += "ignoreCase: " + re.ignoreCase.toString();  
    s += "<br />";  
    s += "multiline: " + re.multiline.toString();  
    s += "<br />";  
    s += "Resulting String: " + r;  
    s += "<br />";  
    s += "<br />";  
    return (s);  
}  
  
document.write(RegExpPropDemo("gi"));  
document.write(RegExpPropDemo("g"));  
```  
  
## <a name="example"></a>Příklad  
 Tady je výsledný výstup.  
  
```JavaScript  
global: true  
ignoreCase: true  
multiline: false  
Resulting String: a batter hit a ball with a bat and a fielder caught a ball with a glove.  
  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Global – vlastnost (regulární výraz)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [Multiline – vlastnost (regulární výraz)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)