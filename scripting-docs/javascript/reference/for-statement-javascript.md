---
title: "pro příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: for_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: loop structures, for statements
ms.assetid: bae0ec40-152e-43f3-969b-3696489ec5c4
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7142dbb8c00a351918d0821c3ca7dba3d7b2acb6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="for-statement-javascript"></a>for – příkaz (JavaScript)
Spouští blok příkazů pro tak dlouho, dokud je splněna zadaná podmínka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
for ([initialization]; [test]; [increment])  
   statement   
```  
  
## <a name="parameters"></a>Parametry  
 `initialization`  
 Volitelné. Výraz. Tento výraz se spustí jenom jednou, před provedením smyčky.  
  
 `test`  
 Volitelné. Logický výraz. Pokud `test` je `true`, `statement` se spustí. Pokud `test` Pokud `false`, ukončení smyčky.  
  
 `increment`  
 Volitelné. Výraz. Výraz přírůstek je spustit na konci každé předávání smyčky.  
  
 `statement`  
 Volitelné. Jeden nebo více příkazů, které mají být provedeny, pokud `test` je **true**. Může být složený příkaz.  
  
## <a name="remarks"></a>Poznámky  
 Obvykle použijete `for` cykly po smyčky, chcete-li být spustit známé stanovený počet. A `for` smyčka je užitečný pro iterování přes pole a pro zpracování sekvenčních provádění.  
  
 Test podmíněného výrazu dojde před provádění smyčky, takže `for` příkaz provede nula či více krát.  
  
 Na kterýkoli řádek v `for` smyčky příkaz blok, můžete použít `break` příkaz pro ukončení smyčky, nebo můžete použít `continue` příkaz k řízení přenosu do další iterace smyčky.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `for` příkaz provede závorkách příkazy následujícím způsobem:  
  
-   První, počáteční hodnota proměnné `i` vyhodnotí.  
  
-   Potom, tak dlouho, dokud hodnota `i` je menší než nebo rovna 9, `document.write` příkazy jsou spouštěny a `i` je již znovu.  
  
-   Když `i` je větší než 9, stav se změní na hodnotu false a ovládací prvek je přenesen mimo smyčku.  
  
```JavaScript  
// i is set to 0 at the start and is incremented by 1 at the  
// end of each iteration.  
// The loop terminates when i is not less than or equal to  
// 9 before a loop iteration.  
for (var i = 0; i <= 9; i++) {  
   document.write (i);  
   document.write (" ");  
}  
  
// Output: 0 1 2 3 4 5 6 7 8 9  
```  
  
## <a name="example"></a>Příklad  
 Všechny výrazy z `for` příkaz jsou volitelné. V následujícím příkladu `for` příkazy vytvoří nekonečnou smyčku a `break` příkaz se používá k ukončení smyčky.  
  
```JavaScript  
var j = 0;  
for (;;) {  
    if (j >= 5) {  
        break;  
    }  
    j++;  
    document.write (j + " ");  
}  
  
// Output: 1 2 3 4 5  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [for... v příkazu](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while – příkaz](../../javascript/reference/while-statement-javascript.md)