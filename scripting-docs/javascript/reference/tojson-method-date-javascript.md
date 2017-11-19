---
title: "tojson – metoda (Date) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: toJSON method
ms.assetid: f91df030-e9c9-425e-8e6d-b46bdda66cb6
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a131c7b248ca0486ab0b3b02d40e4351136c37c9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tojson-method-date-javascript"></a>toJSON – metoda (Date) (JavaScript)
Používané [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md) způsob povolení transformace dat objektu pro serializaci JavaScript Object Notation (JSON).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
objectname.toJSON()  
```  
  
## <a name="parameters"></a>Parametry  
 `objectname`  
 Požadováno. Objekt, pro které JSON je chtěli serializace.  
  
## <a name="remarks"></a>Poznámky  
 `toJSON` Metoda používá `JSON.stringify` funkce. `JSON.stringify`serializuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu na JSON text. Pokud `toJSON` metoda zajišťuje `JSON.stringify`, `toJSON` metoda je volána, když `JSON.stringify` je volána.  
  
 `toJSON` Metoda se jedná o integrovanou člena [datum](../../javascript/reference/date-object-javascript.md) [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objektu. Vrátí řetězec ve formátu ISO data pro časové pásmo UTC (označen příponou Z).  
  
 Můžete přepsat `toJSON` metodu `Date` zadejte, nebo definujte `toJSON` metoda pro jiné typy objektů k dosažení transformaci dat pro konkrétní objekt typu před serializace JSON.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `toJSON` metoda k serializaci hodnoty členů řetězce na velká písmena. `toJSON` Metoda je volána, když `JSON.stringify` je volána.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
  
/* The value of jsonText is:  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `toJSON` metoda, která je členem předdefinované skupiny [datum](../../javascript/reference/date-object-javascript.md) objektu.  
  
```JavaScript  
var dt = new Date('8/24/2009');  
dt.setUTCHours(7, 30, 0);  
var jsonText = JSON.stringify(dt);  
  
/* The value of jsonText is:  
'"2009-08-24T07:30:00Z"'  
*/  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]**Platí pro:** [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Objekt JSON](../../javascript/reference/json-object-javascript.md)   
 [JSON.Parse – funkce](../../javascript/reference/json-parse-function-javascript.md)   
 [JSON.stringify – funkce](../../javascript/reference/json-stringify-function-javascript.md)   
 [Metody jazyka JavaScript](../../javascript/reference/javascript-methods.md)