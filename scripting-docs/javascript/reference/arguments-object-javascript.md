---
title: arguments – objekt (JavaScript) | Microsoft Docs
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
- arguments, arguments object
- arguments object
ms.assetid: 5eb79ca9-bbb8-4a42-aaf5-16a93ecb425f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a5c526d19ad5469d9d099f51cc5a2e2d089814f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789168"
---
# <a name="arguments-object-javascript"></a>arguments – objekt (JavaScript)
Objekt, který reprezentuje argumenty aktuálně prováděné funkce a funkce, které volán.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[function.]arguments[n]  
```  
  
## <a name="parameters"></a>Parametry  
 *funkce*  
 Volitelné. Název aktuálně spuštěných `Function` objektu.  
  
 *n*  
 Požadováno. Index založený na nule hodnoty argument předaný `Function` objektu.  
  
## <a name="remarks"></a>Poznámky  
 Nelze vytvořit explicitní **argumenty** objektu. **Argumenty** objekt pouze k dispozici při vykonávání funkce. **Argumenty** objekt funkce není pole, ale jednotlivé argumenty, které jsou dostupné stejným způsobem jako elementy pole ke kterým se přistupuje. Index  *n*  je ve skutečnosti odkaz na jednu z **0**  ***n***  vlastnosti **argumenty** objektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **argumenty** objektu.  
  
```JavaScript  
function ArgTest(a, b)  
{  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
   s += "<br />";  
  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++)  
   {  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
  
   document.write(s);  
}  
  
ArgTest(1, 2, "hello", new Date())  
  
// Output:  
// Expected Arguments: 2  
// Passed Arguments: 4  
// The individual arguments are: 1 2 hello Tues Jan 8 08:27:09 PST 20xx  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [0... n vlastnosti (arguments)](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md)   
 [callee – vlastnost (arguments)](../../javascript/reference/callee-property-arguments-javascript.md)   
 [Length – vlastnost (arguments)](../../javascript/reference/length-property-arguments-javascript.md)