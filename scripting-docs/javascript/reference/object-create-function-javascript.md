---
title: Object.Create – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- create function [JavaScript]
- Object.create function [JavaScript]
ms.assetid: 0ad31f36-a9ee-444e-b0fe-c87843d03196
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f359908c5c836743e22390580f542df27d7b98e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791652"
---
# <a name="objectcreate-function-javascript"></a>Object.create – funkce (JavaScript)
Vytvoří objekt, který má určeného prototypu a volitelně obsahující zadané vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Object.create(prototype, descriptors)  
```  
  
#### <a name="parameters"></a>Parametry  
 `prototype`  
 Požadováno. Objekt, který chcete použít jako prototypu. Může být `null`.  
  
 `descriptors`  
 Volitelné. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekt, který obsahuje jeden nebo více popisovače vlastnosti.  
  
 A *vlastnosti dat* je vlastnost, která můžete získat a nastavit hodnotu. Popisovač vlastnosti dat obsahuje `value` atribut, plus `writable`, `enumerable`, a `configurable` atributy. Pokud nejsou zadané poslední tři atributy, se ve výchozím nastavení `false`. *Přistupujícího objektu vlastnosti* volá funkci zadaný uživatelem pokaždé, když je hodnota načíst nebo nastavit. Popisovač přistupujícího objektu vlastnosti obsahuje `set` atribut `get` atribut, nebo obojí. Další informace najdete v tématu [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Nový objekt, který má zadaný interní prototypu a obsahuje zadané vlastnosti, pokud existuje.  
  
## <a name="exceptions"></a>Výjimky  
 A `TypeError` je vyvolána výjimka, pokud platí některá z následujících podmínek:  
  
-   `prototype` Argument není objekt a není `null`.  
  
-   Popisovač v `descriptors` argument má `value` nebo `writable` atribut a má `get` nebo `set` atribut.  
  
-   Popisovač v `descriptors` argument má `get` nebo `set` atribut, který není funkce.  
  
## <a name="remarks"></a>Poznámky  
 Pomocí této funkce můžete použít `null``prototype` parametr, aby bylo možné zastavit řetězec prototypu. Objekt vytvořený bude mít žádné prototypu.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří objekt pomocí `null` prototypu a přidá dvě výčtové vlastnosti.  
  
```JavaScript  
var newObj = Object.create(null, {  
            size: {  
                value: "large",  
                enumerable: true  
            },  
            shape: {  
                value: "round",  
                enumerable: true  
            }  
        });  
  
document.write(newObj.size + "<br/>");  
document.write(newObj.shape + "<br/>");  
document.write(Object.getPrototypeOf(newObj));  
  
// Output:  
// large  
// round  
// null  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří objekt, který má stejné interní prototypu jako objekt objektu. Uvidíte, že má stejnou prototyp jako objektu vytvořeny pomocí objekt literálu. [Object.getprototypeof –](../../javascript/reference/object-getprototypeof-function-javascript.md) funkce získá prototyp původní objekt. Chcete-li získat popisovač vlastnost objektu, můžete použít [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
```JavaScript  
var firstLine = { x: undefined, y: undefined };  
  
var secondLine = Object.create(Object.prototype, {  
        x: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            },  
            y: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            }  
});  
  
document.write("first line prototype = " + Object.getPrototypeOf(firstLine));  
document.write("<br/>");  
document.write("second line prototype = " + Object.getPrototypeOf(secondLine));  
  
// Output:  
// first line prototype = [object Object]  
// second line prototype = [object Object]  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří objekt, který má stejné interní prototypu jako objekt tvaru.  
  
```JavaScript  
  
// Create the shape object.  
var Shape = { twoDimensional: true, color: undefined, hasLineSegments: undefined };  
  
var Square = Object.create(Object.getPrototypeOf(Shape));  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.getprototypeof – funkce](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [isPrototypeOf – metoda (Object)](../../javascript/reference/isprototypeof-method-object-javascript.md)   
 [Vytváření objektů](../../javascript/creating-objects-javascript.md)