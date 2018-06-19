---
title: Test – metoda (regulární výraz) (JavaScript) | Microsoft Docs
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
- test
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- test method
ms.assetid: 4f4b6e39-cb1a-4be9-a66f-7b846075580d
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53e2d2c23821cba5149367c7b5a735fa471bf581
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791733"
---
# <a name="test-method-regular-expression-javascript"></a>test – metoda (regulární výraz) (JavaScript)
Vrátí logickou hodnotu určující, zda existuje vzor vyhledávaná řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
rgExp.test(str)   
```  
  
## <a name="parameters"></a>Parametry  
 `rgExp`  
 Požadováno. Instance **regulární výraz** objekt, který obsahuje regulární výraz a příslušné značky.  
  
 `str`  
 Požadováno. Řetězec, na které se má provést hledání.  
  
## <a name="remarks"></a>Poznámky  
 **Testování** metoda zkontroluje, zda existuje v rámci řetězce vzor a vrátí **true** Pokud ano, a **false** jinak.  
  
 Vlastnosti na globální `RegExp` nejsou upraveném objektu **testování** metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **testování** metoda. Pokud chcete použít v tomto příkladu, předejte funkce regulárnímu výrazu a řetězec. Funkce testovat výskytem vzor regulárního výrazu v řetězci, který se vrátí řetězec označující výsledky vyhledávání:  
  
```JavaScript  
function TestDemo(re, teststring)  
{  
   // Test string for existence of regular expression.  
   var found = re.test(teststring)  
  
   // Format the output.  
   var s = "";  
   s += "'" + teststring + "'"  
  
   if (found)  
      s += " contains ";  
   else  
      s += " does not contain ";  
  
   s += "'" + re.source + "'"  
   return(s);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)   
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)