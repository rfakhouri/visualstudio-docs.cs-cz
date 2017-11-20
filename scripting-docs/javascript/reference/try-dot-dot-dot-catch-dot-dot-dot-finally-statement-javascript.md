---
title: "Try... catch... finally – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- try_JavaScriptKeyword
- finally_JavaScriptKeyword
- catch_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- try-catch exception handling, finally block
- try-catch exception handling, about try-catch exception handling
- try-catch exception handling, catch block
- try-catch exception handling
ms.assetid: b7a0a54e-dfaa-4e41-bf25-bcaa43e601fb
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b05f15e593aeb7cb921f6237fad30b589cfdfe66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="trycatchfinally-statement-javascript"></a>try...catch...finally – příkaz (JavaScript)
Nastaví bloky kódu, ve kterých chyby vyvolané jedním blokem jsou zpracovány jiným blokem. Chyby, které jsou vyvolány uvnitř `try` bloku jsou zachyceny v `catch` bloku. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
try {  
    tryStatements  
}  
catch(exception){  
    catchStatements  
}  
finally {  
    finallyStatements  
}  
```  
  
## <a name="parameters"></a>Parametry  
 `tryStatements`  
 Požadováno. Příkazy, u kterých může dojít k chybě.  
  
 `exception`  
 Požadováno. Libovolný název proměnné. Počáteční hodnota `exception` je hodnota této výjimce dojde chyby.  
  
 `catchStatements`  
 Volitelné. Příkazy se budou zpracovávat chyby, ke kterým dochází v přidruženém `tryStatements`.  
  
 `finallyStatements`  
 Volitelné. Příkazy, které jsou bezpodmínečně provedeny po všech ostatních procesech zpracování chyby.  
  
## <a name="remarks"></a>Poznámky  
 `try...catch...finally` Příkaz poskytuje způsob, jak zpracovat některé nebo všechny chyby, které může dojít v každém bloku kódu, při stále běhu kódu. Pokud dojde k chybám, které nejsou zpracovány [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] poskytuje běžná chybová zpráva.  
  
 `try` Blok obsahuje kód, který může vyvolat chybu, když `catch` blok obsahuje kód, který zpracovává některé nebo všechny chyby. Pokud dojde k chybě v `try` bloku řízení programu je předána `catch` bloku. Hodnota `exception` je hodnota chyba, k níž došlo `try` bloku. Pokud nedojde k žádné chybě, kód `catch` nikdy vykonání bloku.  
  
 Chyba až další úroveň můžete předat pomocí `throw` příkaz znovu vyvolá chybu.  
  
 Po všechny příkazy ve `try` provedli bloku a zpracování chyb bylo provedeno `catch` blokovat, příkazy `finally` bloku jsou spouštěny, zda bylo zpracováno k chybě. Kód `finally` bloku záruku, že ke spuštění, pokud dojde k nezpracované chybě (například Chyba spuštění uvnitř **catch** bloku).  
  
## <a name="example"></a>Příklad  
 Následující příklad způsobí, že `ReferenceError` vyvolání výjimky a zobrazí název chyba a jeho zprávu.  
  
```JavaScript  
try {  
    addalert("bad call");  
}  
catch(e) {  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF);  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
  
// Output:  
Error Message: 'addalert' is undefined  
Error Code: 5009  
Error Name: ReferenceError  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak znovu vyvolání chyby, jakož i provádění vnořené `try...catch` bloky. Pokud se chyba z vnořeného `try` bloku předává do vnořeného `catch` blok, který znovu vyvolá výjimku. Vnořeného `finally` bloku se spouští před vnější `catch` bloku zpracovává chyby a na konci vnější `finally` blokovat spuštění.  
  
```JavaScript  
try {  
    document.write("Outer try running...<br/>");  
  
    try {  
        document.write("Nested try running...<br/>");  
        throw new Error(301, "an error");  
    }  
    catch (e) {  
        document.write ("Nested catch caught " + e.message + "<br/>");  
        throw e;  
    }  
    finally {  
        document.write ("Nested finally is running...<br/>");  
    }  
}  
catch (e) {  
    document.write ("Outer catch caught " + e.message + "<br/>");  
}  
finally {  
    document.write ("Outer finally running");  
}  
  
// Output:  
// Outer try running...  
// Nested try running...  
// Nested catch caught error from nested try  
// Nested finally is running...  
// Outer catch caught error from nested try  
// Outer finally running  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
> [!NOTE]
>  Spouštění v režimu Standardy aplikace Internet Explorer 8, **catch** bloku se už nevyžaduje pro `finally` ke spuštění.  
  
## <a name="see-also"></a>Viz také  
 [throw – příkaz](../../javascript/reference/throw-statement-javascript.md)   
 [Skript ostatními konfigurace Průvodce ukázkové aplikace](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)