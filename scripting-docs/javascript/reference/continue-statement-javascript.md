---
title: "Continue – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: continue_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- continue statement
- loop structures, continue statement
ms.assetid: f8a30d9f-e2de-4e1f-8668-4e4cf95f7df9
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 391f919c4d06a6c529bfee34e21ca7238b3c63b7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="continue-statement-javascript"></a>continue – příkaz (JavaScript)
Zastaví na aktuální iteraci smyčky a spustí novou iteraci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
continue [label];  
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné `label` argument určuje příkaz, ke kterému `continue` platí.  
  
 Můžete použít `continue` příkaz pouze uvnitř `while`, `do...while`, **pro**, nebo `for...in` smyčky. Provádění `continue` příkaz zastaví na aktuální iteraci smyčky a pokračuje v toku programu se začátkem smyčky. To má tyto důsledky na různé typy smyčky:  
  
-   `while`a `do...while` smyčky testování jejich stav a v případě hodnoty true provést smyčky znovu.  
  
-   `for`smyčky provést jejich výraz přírůstek a Pokud výraz test je nastavena hodnota true, spouštění smyčky znovu.  
  
-   `for...in`smyčky pokračovat na další pole zadanou proměnnou a znovu spusťte smyčky.  
  
## <a name="examples"></a>Příklady  
 V tomto příkladu smyčku opakuje od 1 do 9. Příkazy mezi `continue` a na konci `for` body jsou přeskočeny z důvodu použití `continue` příkaz společně s výraz `(i < 5)`.  
  
```JavaScript  
for (var i = 1; i < 10; i++) {  
    if (i < 5) {  
        continue;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 5 6 7 8 9  
```  
  
 V následujícím kódu `continue` příkaz odkazuje na `for` smyčky, která předchází `Inner:` popisek. Když `j` je 24, `continue` příkaz způsobuje, který `for` přejít do další iterace smyčky. Čísla 21 až 23 a 25 prostřednictvím 30 tisku na každém řádku.  
  
```JavaScript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
             continue Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
//Output:  
//i: 1 j: 21 22 23 25 26 27 28 29 30   
//i: 2 j: 21 22 23 25 26 27 28 29 30   
//i: 3 j: 21 22 23 25 26 27 28 29 30   
//i: 4 j: 21 22 23 25 26 27 28 29 30   
//i: 5 j: 21 22 23 25 26 27 28 29 30   
//i: 6 j: 21 22 23 25 26 27 28 29 30   
//i: 7 j: 21 22 23 25 26 27 28 29 30   
//i: 8 j: 21 22 23 25 26 27 28 29 30   
//i: 9 j: 21 22 23 25 26 27 28 29 30   
//i: 10 j: 21 22 23 25 26 27 28 29 30  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Příkaz BREAK](../../javascript/reference/break-statement-javascript.md)   
 [do... while – příkaz](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [for... v příkazu](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Příkaz s popiskem](../../javascript/reference/labeled-statement-javascript.md)   
 [while – příkaz](../../javascript/reference/while-statement-javascript.md)