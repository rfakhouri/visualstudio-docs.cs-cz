---
title: "Length – vlastnost (Function) (JavaScript) | Microsoft Docs"
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
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Length property
- length property (function)
ms.assetid: fdc8e1c9-0dac-4e1b-ba3a-11073c37ef63
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fbd0334c18da2c6ef8de8366555d79f791e6855
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-function-javascript"></a>length – vlastnost (Function) (JavaScript)
Získá počet argumentů pro funkci definován.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
functionName.length  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované *%{FunctionName/* je název funkce.  
  
 **Délka** vlastnost funkce se inicializuje pomocí skriptovací stroj pro počet argumentů v definici funkcí, když je vytvořena instance funkce.  
  
 Co se stane, když je volána funkce s počtem argumentů, které se liší od hodnoty z jeho **délka** vlastnost závisí na funkce.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **délka** vlastnost:  
  
```JavaScript  
function ArgTest(a, b){  
    var s = "";  
  
    s += "Expected Arguments: " + ArgTest.length;  
    s += "<br />";  
    s += "Passed Arguments: " + arguments.length;  
  
    return s;  
}  
  
document.write(ArgTest(1, 2));  
  
// Output:   
// Expected Arguments: 2  
// Passed Arguments: 2  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [arguments – vlastnost (Function)](../../javascript/reference/arguments-property-function-javascript.md)   
 [Length – vlastnost (pole)](../../javascript/reference/length-property-array-javascript.md)   
 [Length – vlastnost (String)](../../javascript/reference/length-property-string-javascript.md)