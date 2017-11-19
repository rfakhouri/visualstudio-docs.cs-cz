---
title: "instanceof – operátor (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: instanceof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: instanceOf operator
ms.assetid: 92467bdc-56b5-42dc-adbd-a219776454d2
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 672047cb066a812d16edc693638c3d6d8295798b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="instanceof-operator-javascript"></a>instanceof – operátor (JavaScript)
Vrátí logickou hodnotu, která určuje, zda je objekt instancí určité třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = object instanceof class  
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Požadováno. Všechny proměnné.  
  
 `object`  
 Požadováno. Jakýkoli objekt výraz.  
  
 `class`  
 Požadováno. Existuje definovanou třídu objektu.  
  
## <a name="remarks"></a>Poznámky  
 `instanceof` Vrátí operátor `true` Pokud `object` je instance `class`. Vrátí `true` Pokud `true` Pokud `class` se nachází v řetězci prototyp objektu. Vrátí `false` Pokud `object` není instanci `class`, nebo pokud `object` je `null`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `instanceof` operátor.  
  
```JavaScript  
function objTest(obj){  
    var i, t, s = "";  
    t = new Array();  
    t["Date"] = Date;  
    t["Object"] = Object;  
    t["Array"] = Array;  
        for (i in t){  
            if (obj instanceof t[i]) {   
                s += "obj is an instance of " + i + "<br/>";  
            }  
            else {  
                s += "obj is not an instance of " + i + "<br/>";  
        }  
    }  
    return(s);  
}  
  
var obj = new Date();  
document.write(objTest(obj));  
  
// Output:   
// obj is an instance of Date  
// obj is an instance of Object  
// obj is not an instance of Array  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)