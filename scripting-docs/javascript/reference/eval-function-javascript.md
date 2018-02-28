---
title: "Eval – funkce (JavaScript) | Microsoft Docs"
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
- eval
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- eval function
- parsing, code
- parser
ms.assetid: 85587e39-9325-4b75-b9f9-9d7d475a2120
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 388e486f58bb70fd192701060a5faefaed8bd98e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="eval-function-javascript"></a>eval – funkce (JavaScript)
Vyhodnotí [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kód a provede ji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
eval(codeString)   
```  
  
## <a name="parameters"></a>Parametry  
 `codeString`  
 Požadováno. A `String` hodnotu, která obsahuje platné [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kódu.  
  
## <a name="remarks"></a>Poznámky  
 `eval` Funkce umožňuje dynamické provádění [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] zdrojový kód.  
  
 `codeString` Řetězec je analyzován pomocí [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] analyzátor a spustit.  
  
 Předaný kód `eval` funkce se spustí ve stejné oblasti jako volání `eval` funkce.  
  
 Pokud je to možné, použijte [funkce JSON.parse](../../javascript/reference/json-parse-function-javascript.md) deserializovat text JavaScript Object Notation (JSON). `JSON.parse` Funkce je bezpečnější a spustí rychleji než `eval` funkce.  
  
## <a name="example"></a>Příklad  
 Následující kód inicializuje proměnnou `myDate` na testovací datum.  
  
```JavaScript  
var dateFn = "Date(1971,3,8)";  
var myDate;  
eval("myDate = new " + dateFn + ";");  
  
document.write(myDate);  
  
// Output: Thu Apr 8 00:00:00 PDT 1971  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [String – objekt](../../javascript/reference/string-object-javascript.md)