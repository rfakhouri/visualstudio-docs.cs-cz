---
title: "in – operátor (JavaScript) | Microsoft Docs"
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
- in_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- in operator
ms.assetid: dcd8f901-96b8-4c91-848b-b1ec0ab1c11c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eefcd4c53d2e3366a26f0d8dfb099f59038507ae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="in-operator-javascript"></a>in – operátor (JavaScript)
Testy existence vlastnost v objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = property in object  
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Požadováno. Všechny proměnné.  
  
 `property`  
 Požadováno. Výraz, který se vyhodnocuje řetězcového výrazu.  
  
 `object`  
 Požadováno. Libovolný objekt.  
  
## <a name="remarks"></a>Poznámky  
 `in` Operátor určuje, zda objekt obsahuje vlastnost s názvem `property`. Také určuje, zda vlastnost je částí objektu prototypu řetězu. Další informace o objektu prototypy najdete v tématu [prototypy a jejich dědičnost](../../javascript/advanced/prototypes-and-prototype-inheritance.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `in` operátor:  
  
```JavaScript  
// Create an object that has some properties.  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 0234";  
  
if ("phone" in myObject)  
   document.write ("property is present");  
else  
   document.write ("property is not present");  
  
// Output: property is present  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)