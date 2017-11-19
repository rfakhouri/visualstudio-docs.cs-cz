---
title: "Compile – metoda (regulární výraz) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: compile
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- regular expressions, compiling
- Compile method
- compiling source code, regular expressions
ms.assetid: dc28cae3-478d-49b5-b5ea-203e5edfe195
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b8de23a9e4f0e03fbf042195867ad9426e4c6bb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="compile-method-regular-expression-javascript"></a>compile – metoda (regulární výraz) (JavaScript)
Zkompiluje regulární výraz do interní formát rychlejší.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
rgExp.compile(pattern, [flags])   
```  
  
## <a name="parameters"></a>Parametry  
 `rgExp`  
 Požadováno. Instance **regulární výraz** objektu. Může být název proměnné nebo literál.  
  
 *vzor*  
 Požadováno. Řetězcového výrazu obsahujícího vzor regulárního výrazu mají být zkompilovány, do  
  
 `flags`  
 Volitelné. K dispozici příznaky, které mohou být spojeny, jsou:  
  
-   g (globální vyhledávání pro všechny výskyty *vzor*)  
  
-   i (ignorovat velká /)  
  
-   m (multiline vyhledávání)  
  
## <a name="remarks"></a>Poznámky  
 **Zkompilovat** metoda převede *vzor* do interní formát rychlejší. To umožňuje efektivnější využití regulárních výrazů v smyčky, například. Kompilované regulární výraz urychluje věcí při opakovaném použití stejný výraz opakovaně. Žádné výhody je získávají, ale pokud se změní regulární výraz.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **zkompilovat** metoda:  
  
```JavaScript  
function CompileDemo(){  
   var rs;  
   var s = "AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPp"  
   // Create regular expression for uppercase only.  
   var r = new RegExp("[A-Z]", "g");  
   var a1 = s.match(r)              // Find matches.  
   // Compile the regular expression for lowercase only.  
   r.compile("[a-z]", "g");  
// Find matches.  
   var a2 = s.match(r)                
   return(a1 + "\n" + a2);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)