---
title: "Length – vlastnost (arguments) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- length property (arguments)
- Length property
ms.assetid: 3cf36823-15bc-489b-a951-24c4923d9dba
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cede75a91244442f5f28ec9f71b7128814bed5d2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-arguments-javascript"></a>length – vlastnost (arguments) (JavaScript)
Vrátí skutečný počet argumentů pro funkci předaná volající funkcí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[function.]arguments.length  
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné *funkce* argument je název aktuálně spuštěných `Function` objektu.  
  
 **Délka** vlastnost **argumenty** objekt se inicializuje pomocí skriptovacího stroje skutečný počet argumentů předaných `Function` objektu při provádění začíná v této funkce.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **délka** vlastnost **argumenty** objektu. Abyste plně porozuměli tomu v příkladu, předejte další argumenty funkce než 2 argumenty očekávání:  
  
```JavaScript  
function ArgTest(a, b){  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
  
   document.write (s);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [objekt arguments](../../javascript/reference/arguments-object-javascript.md)&#124; [Funkce objektu](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [arguments – vlastnost (Function)](../../javascript/reference/arguments-property-function-javascript.md)   
 [Length – vlastnost (pole)](../../javascript/reference/length-property-array-javascript.md)   
 [Length – vlastnost (String)](../../javascript/reference/length-property-string-javascript.md)