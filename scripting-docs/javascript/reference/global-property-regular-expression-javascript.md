---
title: "Global – vlastnost (regulární výraz) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Global
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: global property
ms.assetid: 76a0f115-0d89-4aca-86d5-932895c6d649
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e2b0256fea60b7ab998c504e79565fc7028cd98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="global-property-regular-expression-javascript"></a>global – vlastnost (regulární výraz) (JavaScript)
Vrátí logickou hodnotu udávající, stav příznak globální (**g**) používá s regulárním výrazem. Výchozí hodnota je **false**. Jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
rgExp.global  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `rgExp` odkaz je instance **regulární výraz** objektu.  
  
 `global` Vlastnost vrátí **true** Pokud je nastaven pro regulární výraz příznak globální a vrátí **false** Pokud není.  
  
 Příznak globální, pokud se použije, označuje, že hledání by měl zjistit všechny výskyty vzoru v rámci vyhledávaná řetězce, nikoli pouze první z nich. Tím se taky říká globální odpovídající.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `global` vlastnost. Pokud předáte **g** ve funkci vidíte níže, všechny instance aplikace word "na" jsou nahrazena slovo "a". Všimněte si, že "The" na začátku řetězce není nahradit, protože **i** (ignorovat velká /) příznak není předaný funkci.  
  
 Tato funkce zobrazí podmínku vlastnosti související s povolenou regulární výraz příznaky, které jsou **g**, **i**, a **m**. Funkce také zobrazí řetězec s všechny nahrazené provedeny.  
  
```JavaScript  
function RegExpPropDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The batter hit the ball with the bat ";  
   ss += "and the fielder caught the ball with the glove.";  
  
   //Replace "the" with "a".  
   var re = new RegExp("the", flag);  
   var r = ss.replace(re, "a");          
  
   // Output the resulting string and the flags.  
   var s = "";  
   s += "global: " + re.global.toString();  
   s += "<br />";  
   s += "ignoreCase: " + re.ignoreCase.toString();  
   s += "<br />";  
   s += "multiline: " + re.multiline.toString();  
   s += "<br />";  
   s += "Resulting String: " + r;  
  
   return (s);  
}  
  
document.write(RegExpPropDemo("g"));  
```  
  
## <a name="example"></a>Příklad  
 Tady je výsledný výstup.  
  
```JavaScript  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [IgnoreCase – vlastnost (regulární výraz)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [Multiline – vlastnost (regulární výraz)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)