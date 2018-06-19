---
title: Search – metoda (String) (JavaScript) | Microsoft Docs
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
- search
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- search method
ms.assetid: 1cae0fbc-3319-4327-ba4e-d5fa2c4a9ba0
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 730fb1604147b56fc5ab1e312bf7a6dfb5487a5a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791427"
---
# <a name="search-method-string-javascript"></a>search – metoda (String) (JavaScript)
Na první shodu dílčí řetězec najde v hledání regulárního výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringObj.search(rgExp)   
```  
  
## <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. `String` Objekt nebo řetězcový literál, na které se má provést hledání.  
  
 `rgExp`  
 Požadováno. Instance **regulární výraz** objekt, který obsahuje regulární výraz a příslušné značky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je nalezena shoda, **vyhledávání** metoda vrátí celočíselnou hodnotu, která určuje posun od začátku řetězce, kde došlo k chybě na první shodu. Pokud není nalezena žádná shoda, vrátí hodnotu -1.  
  
## <a name="remarks"></a>Poznámky  
 Můžete také nastavit `i` příznak, který způsobuje, že výsledky vyhledávání na se velká a malá písmena.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **vyhledávání** metoda.  
  
```JavaScript  
var src = "is but a Dream within a dream";  
var re = /dream/;  
var pos = src.search(re);  
document.write(pos);  
document.write("<br/>");  
  
re = /dream/i;  
pos = src.search(re);  
document.write(pos);  
  
// Output:   
// 24   
// 9  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Exec – metoda (regulární výraz)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [Match – metoda (String)](../../javascript/reference/match-method-string-javascript.md)   
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [replace – metoda (String)](../../javascript/reference/replace-method-string-javascript.md)   
 [Test – metoda (regulární výraz)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Programování regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)