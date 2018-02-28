---
title: "BREAK – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- break_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- break statement
ms.assetid: 5be0f2a8-5fe7-4a6c-89af-ca20a925ce87
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f085a4e51309bf9a060e9ffa352c6ae85924237
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="break-statement-javascript"></a>break – příkaz (JavaScript)
Ukončí aktuální smyčky, nebo, pokud ve spojení s `label`, ukončí přidružený příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
break [label];  
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné `label` argument určuje popisek rozbalíte z příkazu.  
  
 Obvykle se používá `break` příkaz v `switch` příkazy a v `while`, `for`, `for...in`, nebo `do...while` smyčky. Nejčastěji použijete `label` argument `switch` příkazy, ale mohou být používány s příkazy, ať už jednoduché nebo složené.  
  
 Provádění `break` příkaz ukončí z aktuální smyčky nebo příkazu a začíná příkaz okamžitě po spuštění skriptu.  
  
## <a name="examples"></a>Příklady  
 V tomto příkladu jsou nastaveny čítač na počet od 1 do 99; ale `break` příkaz ukončí smyčky po 14 počty.  
  
```JavaScript  
for (var i = 1; i < 100; i++) {  
    if (i == 15) {  
        break;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 1234567891011121314  
```  
  
 V následujícím kódu `break` příkaz odkazuje na `for` smyčky, která předchází `Inner:` příkaz. Když `j` rovná 24, `break` příkaz způsobí, že běh programu pro ukončení tohoto smyčky. Čísla 21 až 23 tisku na každém řádku.  
  
```JavaScript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
            break Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
// Output:   
// i: 1 j: 21 22 23   
// i: 2 j: 21 22 23   
// i: 3 j: 21 22 23   
// i: 4 j: 21 22 23   
// i: 5 j: 21 22 23   
// i: 6 j: 21 22 23   
// i: 7 j: 21 22 23   
// i: 8 j: 21 22 23   
// i: 9 j: 21 22 23   
// i: 10 j: 21 22 23  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Continue – příkaz](../../javascript/reference/continue-statement-javascript.md)   
 [do... while – příkaz](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [for... v příkazu](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Příkaz s popiskem](../../javascript/reference/labeled-statement-javascript.md)   
 [while – příkaz](../../javascript/reference/while-statement-javascript.md)