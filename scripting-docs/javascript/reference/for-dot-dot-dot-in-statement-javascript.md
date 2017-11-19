---
title: "for... v příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- iteration statements, for...in statement
- loop structures, for...in statements
ms.assetid: 1b51a0ce-89f7-4a69-88ed-017b47dc398f
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9c3ce78def6ab91256ff724a4acc87b7cf19ba2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="forin-statement-javascript"></a>for...in – příkaz (JavaScript)
Provede jeden nebo více příkazů pro každou vlastnost objektu nebo každý element pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
for (variable in [object | array]) {  
    statements   
}  
```  
  
## <a name="parameters"></a>Parametry  
 `variable`  
 Požadováno. Proměnné, která může být jakýkoli název vlastnosti z `object` nebo všechny index elementu `array`.  
  
 `object`, `array`  
 Volitelné. Objekt nebo pole, přes který k iteraci v.  
  
 `statements`  
 Volitelné. Jeden nebo více příkazů, které mají být provedeny pro každou vlastnost `object` nebo jednotlivé prvky `array`. Může být složený příkaz.  
  
## <a name="remarks"></a>Poznámky  
 Na začátku každé iteraci smyčky, hodnota `variable` je další název vlastnosti `object` nebo další index elementu `array`. Pak můžete použít `variable` v příkazů uvnitř smyčky, chcete-li vlastnost `object` nebo elementu `array`.  
  
 Vlastnosti objektu nejsou přiřazeni determinate způsobem. Určité vlastnosti jeho index nelze zadat jenom podle názvu vlastnosti.  
  
 Iterace v rámci pole se provádí v pořadí element, který je 0, 1, 2.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `for...in` příkaz s objektem použít jako asociativní pole.  
  
```JavaScript  
// Initialize object.  
a = {"a" : "Athens" , "b" : "Belgrade", "c" : "Cairo"}  
  
// Iterate over the properties.  
var s = ""  
for (var key in a) {  
    s += key + ": " + a[key];  
    s += "<br />";  
    }  
document.write (s);  
  
// Output:  
// a: Athens  
// b: Belgrade  
// c: Cairo  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje použití `for ... in` příkaz, který má iterovat `Array` objekt, který má expando vlastnosti.  
  
```JavaScript  
// Initialize the array.  
var arr = new Array("zero","one","two");  
  
// Add a few expando properties to the array.  
arr["orange"] = "fruit";  
arr["carrot"] = "vegetable";  
  
// Iterate over the properties and elements.  
var s = "";  
for (var key in arr) {  
    s += key + ": " + arr[key];  
    s += "<br />";  
}  
  
document.write (s);  
  
// Output:  
//   0: zero  
//   1: one  
//   2: two  
//   orange: fruit  
//   carrot: vegetable  
```  
  
> [!NOTE]
>  Použití `Enumerator` objekt Iterujte přes kolekci členů.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [while – příkaz](../../javascript/reference/while-statement-javascript.md)