---
title: __Proto –__ – vlastnost (Object) (JavaScript) | Microsoft Docs
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
- __proto__
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 97c3f84d-125e-4905-b921-b021264964ee
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f8659c7a4ece5e30378838f20341ec6712f77ca3
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
ms.locfileid: "29899572"
---
# <a name="proto-property-object-javascript"></a>__Proto –__ – vlastnost (Object) (JavaScript)
Obsahuje odkaz na interní prototyp zadaného objektu.  

> [!WARNING]
> `__proto__` Vlastnost je starší verze funkce. Použití [Object.getprototypeof –](../reference/object-getprototypeof-function-javascript.md) místo.
  
## <a name="syntax"></a>Syntaxe  
  
```  
object.__proto__  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, na kterém chcete nastavit prototypu.  
  
## <a name="remarks"></a>Poznámky  
 `__proto__` Vlastnost lze nastavit prototyp objektu.  
  
 Objekt nebo funkce dědí všechny metody a vlastnosti nové prototyp, společně s všechny metody a vlastnosti v řetězci prototypu nové prototypu. Objekt může mít pouze jeden prototyp (není včetně zděděné prototypy v řetězu prototypu), takže při volání `__proto__` vlastnost, nahradíte předchozí prototypu.  
  
 Prototyp lze nastavit pouze pro objekt rozšiřitelné. Další informace najdete v tématu [Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md).  
  
> [!NOTE]
>  `__proto__` Název vlastnosti zahájení a ukončení dvě podtržítka.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak nastavit prototyp objektu.  
  
```JavaScript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
if (console && console.log) {  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns true  
    rec.__proto__ = Object.prototype;  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns false  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak k přidání vlastností do objektu jejich přidáním do prototypu.  
  
```JavaScript  
var proto = { y: 2 };  
  
var obj = { x: 10 };  
obj.__proto__ = proto;  
  
proto.y = 20;  
proto.z = 40;  
  
if (console && console.log) {  
    console.log(obj.x === 10);  // Returns true  
    console.log(obj.y === 20);  // Returns true  
    console.log(obj.z === 40);  // Returns true  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu přidá vlastnosti, které chcete `String` objektu nastavením nové prototyp na něm.  
  
```JavaScript  
var stringProp = { desc: "description" };  
  
String.__proto__ = stringProp;  
var s1 = "333";  
var s2 = new String("333");  
  
if (console && console.log) {  
  
    console.log(String.desc === "description"); // Returns true  
    console.log(s1.desc === "description");     // Returns false  
    console.log(s2.desc === "description");     // Returns false  
  
    s1.__proto__ = String;  // Can't be set.  
    s2.__proto__ = String;  
  
    console.log(s1.desc === "description"); // Returns false  
    console.log(s2.desc === "description"); // Returns true  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Prototypy a dědičnost prototypů](../../javascript/advanced/prototypes-and-prototype-inheritance.md)