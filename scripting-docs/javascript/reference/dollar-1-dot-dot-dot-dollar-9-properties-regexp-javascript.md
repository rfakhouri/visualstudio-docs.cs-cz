---
title: "$1... $9 – vlastnosti (RegExp) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: $1...$9
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: $1...$9 properties
ms.assetid: 8bd84851-f62f-4eb1-a93d-b67135ea091a
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc1926d6281c9003c432c9c9e89a73a48a584ef4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="19-properties-regexp-javascript"></a>$1...$9 – vlastnosti (RegExp) (JavaScript)
Vrácení že devět naposledy zvyklí části během porovnávání vzorů nalezen. Jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
RegExp.$n   
```  
  
## <a name="parameters"></a>Parametry  
 `RegExp`  
 Vždy globální `RegExp` objektu.  
  
 `n`  
 Jakékoliv celé číslo od 1 do 9.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty **$1... $9** jsou upraveny vlastnosti vždy, když je proveden shoda úspěšné v závorkách. Vzor regulárního výrazu možné zadat libovolný počet dílčích řetězců v závorkách, ale pouze nejnovější devět mohou být uloženy.  
  
## <a name="example"></a>Příklad  
 Následující příklad provádí hledání regulárního výrazu. Zobrazí odpovídá a submatches z na globální `RegExp` objektu. Submatches jsou odpovídá úspěšné závorky, které jsou součástí `$1...$9` vlastnosti. V příkladu se také zobrazí odpovídá a submatches z pole, která je vrácena `exec` metoda.  
  
```JavaScript  
var newLine = "<br />";  
  
var re = /(\w+)@(\w+)\.(\w+)/g  
var src = "Please send mail to george@contoso.com and someone@example.com. Thanks!"  
  
var result;  
var s = "";  
  
// Get the first match.  
result = re.exec(src);  
  
while (result != null) {  
    // Show the entire match.  
    s += newLine;  
  
    // Show the match and submatches from the RegExp global object.  
    s += "RegExp.lastMatch: " + RegExp.lastMatch + newLine;  
    s += "RegExp.$1: " + RegExp.$1 + newLine;  
    s += "RegExp.$2: " + RegExp.$2 + newLine;  
    s += "RegExp.$3: " + RegExp.$3 + newLine;  
  
    // Show the match and submatches from the array that is returned  
    // by the exec method.  
    for (var index = 0; index < result.length; index++) {  
        s +=  index + ": ";  
        s += result[index];  
        s += newLine;  
    }  
  
    // Get the next match.  
    result = re.exec(src);  
}  
document.write(s);  
  
// Output:  
//  RegExp.lastMatch: george@contoso.com  
//  RegExp.$1: george  
//  RegExp.$2: contoso  
//  RegExp.$3: com  
//  0: george@contoso.com  
//  1: george  
//  2: contoso  
//  3: com  
  
//  RegExp.lastMatch: someone@example.com  
//  RegExp.$1: someone  
//  RegExp.$2: example  
//  RegExp.$3: com  
//  0: someone@example.com  
//  1: someone  
//  2: example  
//  3: com  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)