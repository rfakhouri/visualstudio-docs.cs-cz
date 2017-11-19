---
title: "rightcontext – vlastnost ($& č. 39;) (RegExp) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: $'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: rightContext property ($')
ms.assetid: 6999c056-d18c-4583-9dd9-8fbb6d3d0ee7
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d47ea5dd67de9d73ab59b615c567ad3a7a96fb7b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="rightcontext-property-39-regexp-javascript"></a>rightcontext – vlastnost ($& č. 39;) (RegExp) (JavaScript)
Vrací znaky z pozice následující poslední shody na konec vyhledávaná řetězec. Jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
RegExp.rightContext  
```  
  
## <a name="remarks"></a>Poznámky  
 Objekt přidružený k této vlastnosti je vždy na globální `RegExp` objektu.  
  
 Počáteční hodnota **rightcontext –** vlastnost je prázdný řetězec. Hodnota **rightcontext –** změny vlastností vždy, když je proveden úspěšně shody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **rightcontext –** vlastnost:  
  
```JavaScript  
// Create the regular expression pattern.  
var re = new RegExp("d(b+)(d)","ig");  
var str = "cdbBdbsbdbdz";  
  
// Perform the search.  
var arr = re.exec(str);  
  
// Print the output.  
var s = ""   
s += "$1: " + RegExp.$1 + "<br />";  
s += "$2: " + RegExp.$2 + "<br />";  
s += "$3: " + RegExp.$3 + "<br />";  
s += "input: " + RegExp.input + "<br />";  
s += "lastMatch: " + RegExp.lastMatch + "<br />";  
s += "leftContext: " + RegExp.leftContext + "<br />";  
s += "rightContext: " + RegExp.rightContext + "<br />";   
s += "lastParen: " + RegExp.lastParen + "<br />";  
  
document.write(s);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [$1... $9 – vlastnosti (RegExp)](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md)   
 [index – vlastnost (RegExp)](../../javascript/reference/index-property-regexp-javascript.md)   
 [Input – vlastnost ($_) (RegExp)](../../javascript/reference/input-property-dollar-regexp-javascript.md)   
 [lastIndex – vlastnost (RegExp)](../../javascript/reference/lastindex-property-regexp-javascript.md)   
 [lastmatch – vlastnost ($&) (RegExp)](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md)   
 [lastparen – vlastnost ($ +) (RegExp)](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md)   
 [leftcontext – vlastnost ($') (RegExp)](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md)