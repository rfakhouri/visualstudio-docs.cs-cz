---
title: Switch – příkaz (JavaScript) | Microsoft Docs
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
- switch_JavaScriptKeyword
- default_JavaScriptKeyword
- case_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- switch statement
ms.assetid: 61f80e8b-3739-4146-a893-c2832d92b28c
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a301fc8bcc72b48c6ba8e999c0ebb70fe9d92b41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791904"
---
# <a name="switch-statement-javascript"></a>switch – příkaz (JavaScript)
Umožňuje provádění jeden nebo více příkazů, když hodnota zadaného výrazu odpovídá štítek.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
switch (expression) {  
    case label :  
        statementlist  
    case label :  
    default :  
        statementlist  
}   
```  
  
## <a name="parameters"></a>Parametry  
 `expression`  
 Výraz, který má být vyhodnocen.  
  
 `label`  
 Identifikátor k porovnání `expression`. Pokud `label` je `expression`, provádění začíná `statementlist` ihned po dvojtečkou a bude pokračovat, dokud buď zjistí `break` příkaz, který je volitelné, nebo konci `switch` příkaz.  
  
 `statementlist`  
 Jeden nebo více příkazů ke spuštění.  
  
## <a name="remarks"></a>Poznámky  
 Použití `default` klauzule zajistit výpis, který chcete provést, pokud žádná z popisek hodnoty odpovídá `expression`. Může vyskytovat kdekoli v rámci `switch` blok kódu.  
  
 Nula nebo více `label` bloky může být určen. Pokud žádné `label` odpovídá hodnotě `expression`a `default` případ není zadán, jsou provedeny žádné příkazy.  
  
 Provádění toků prostřednictvím `switch` příkaz následujícím způsobem:  
  
-   Vyhodnocení `expression` a podívejte se na `label` v pořadí, dokud je nalezena shoda.  
  
-   Pokud `label` hodnota se rovná `expression`, provést jeho doplňujícími `statementlist`.  
  
     Pokračovat v provádění až `break` příkaz je zjistil, nebo `switch` příkaz zakončení. To znamená, že více `label` bloky jsou provést, pokud `break` příkaz nepoužívá.  
  
-   Pokud žádné `label` rovná `expression`, přejděte na `default` případu. Pokud není žádná `default` případ, přejděte na poslední krok.  
  
-   Na konci následující příkaz v provádění pokračovat `switch` blok kódu.  
  
## <a name="example"></a>Příklad  
 Následující příklad testy pro tento typ objektu.  
  
```JavaScript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
            break;  
        case Number:  
            document.write("Object is a Number.");  
            break;  
        case String:  
            document.write("Object is a String.");  
            break;  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.  
  
// Output when obj is a Number:  
// Object is a Number.  
  
// Output when obj is a String:  
// Object is a String.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, co se stane, když nepoužijete `break` příkaz.  
  
```JavaScript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
        case Number:  
            document.write("Object is a Number.");  
        case String:  
            document.write("Object is a String.");  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a Number:  
// Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a String:  
// Object is a String.Object is unknown.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Příkaz BREAK](../../javascript/reference/break-statement-javascript.md)   
 [If... else – příkaz](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)