---
title: "do... while – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: do_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- terminating loops
- loop structures, do and do-while
ms.assetid: 8b7782ba-fbad-48cd-9639-193566da6ae5
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 895d98a3de3a6691ce60bf0456bb838403619f88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="dowhile-statement-javascript"></a>do...while – příkaz (JavaScript)
Spustí příkaz bloku jednou a pak opakuje provádění smyčky, dokud podmínky výraz vyhodnocen jako `false`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
do {  
    statement  
}  
while (expression) ;   
```  
  
## <a name="parameters"></a>Parametry  
 `statement`  
 Požadováno. Příkaz tak, aby provést, pokud `expression` je `true`. Může být složený příkaz.  
  
 `expression`  
 Požadováno. Výraz, který může být převeden na logickou hodnotu `true` nebo `false`. Pokud `expression` je `true`, smyčky se znovu spustí. Pokud `expression` je `false`, ukončení smyčky.  
  
## <a name="remarks"></a>Poznámky  
 Na rozdíl od `while` příkaz, `do...while` smyčky se spustí jednou předtím, než je vyhodnocena podmíněným výrazem.  
  
 Na kterýkoli řádek v `do...while` blok, můžete použít `break` příkaz způsobí toku programu pro ukončení smyčky, nebo můžete použít `continue` příkaz, který má přejít přímo na `while` výraz.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu, příkazy v `do...while` smyčky pokračovat stejně dlouho jako proměnnou provést `i` je menší než 10.  
  
```JavaScript  
var i = 0;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu jsou příkazy uvnitř smyčky spustit jednou, i když není splněna podmínka.  
  
```JavaScript  
var i = 10;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 10  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Příkaz BREAK](../../javascript/reference/break-statement-javascript.md)   
 [Continue – příkaz](../../javascript/reference/continue-statement-javascript.md)   
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [for... v příkazu](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while – příkaz](../../javascript/reference/while-statement-javascript.md)   
 [Příkaz s popiskem](../../javascript/reference/labeled-statement-javascript.md)