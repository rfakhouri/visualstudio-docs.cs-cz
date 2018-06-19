---
title: arguments – vlastnost (Function) (JavaScript) | Microsoft Docs
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
- arguments
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arguments, arguments property
- Arguments property
ms.assetid: efc7a1ee-0880-4f05-b0f2-808f31a4af1d
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b0b18fb8164639119e5db5e7a5d76b4280f9c9d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788865"
---
# <a name="arguments-property-function-javascript"></a>arguments – vlastnost (Function) (JavaScript)
Získá argumenty pro aktuálně spuštěných `Function` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
function.arguments  
```  
  
## <a name="remarks"></a>Poznámky  
 `function` Argument je název aktuálně prováděné funkce a lze vynechat.  
  
 Tato vlastnost umožňuje funkci pro zpracování proměnný počet argumentů. **Délka** vlastnost `arguments` objekt obsahuje počet argumentů předaný funkci. Jednotlivé argumenty, které jsou součástí `arguments` objekt dostupný stejným způsobem, jako jsou přístupné prvků pole.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `arguments` vlastnost:  
  
```JavaScript  
function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
//Output: function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
// Output: The individual arguments are: 1 2 hello  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [arguments – objekt](../../javascript/reference/arguments-object-javascript.md)   
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)