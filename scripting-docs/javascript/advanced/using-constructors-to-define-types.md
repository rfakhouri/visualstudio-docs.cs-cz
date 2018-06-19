---
title: Definování typů pomocí konstruktorů | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- creating objects, constructor functions
- constructor functions
- functions, constructor functions
- objects, creating [JavaScript]
- constructors, creating
ms.assetid: e869702e-4caf-4513-8dd5-fe690535f8aa
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bff42606fda27e00a537cc227a0b636e016f7c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788820"
---
# <a name="using-constructors-to-define-types"></a>Definování typů pomocí konstruktorů
Konstruktor je funkce, která vytvoří instanci konkrétní typ [objekt](../../javascript/objects-and-arrays-javascript.md). Vyvolat konstruktor s **nové** – klíčové slovo. Zde je několik příkladů konstruktorů s předdefinovanými objekty jazyka JavaScript a vlastními objekty.  
  
## <a name="constructor-examples"></a>Příklady konstruktorů  
  
```JavaScript  
// Creates a generic object.  
var myObject = new Object();  
// Creates a Date object.  
var myBirthday = new Date(1961, 5, 10);  
// Creates a user defined object.  
var myCar = new Car();  
```  
  
 Obsahuje funkci konstruktoru **to** – klíčové slovo, což je odkaz na nově vytvořený objekt prázdný. Inicializuje nový objekt vytvořením vlastností a přidělením počátečních hodnot. Konstruktor vrátí odkaz na jím vytvořený objekt.  
  
## <a name="writing-constructors"></a>Zápis konstruktorů  
 Můžete vytvořit objekty pomocí **nové** operátor ve spojení s předdefinované funkce konstruktoru, jako **Object()**, **Date()**, a **Function()** . Můžete také vytvořit vlastní funkce konstruktoru, které definují sadu vlastností a metod. Zde je příklad vlastního konstruktoru.  
  
```JavaScript  
function Circle (xPoint, yPoint, radius) {  
    this.x = xPoint;  // The x component of the center of the circle.  
    this.y = yPoint;  // The y component of the center of the circle.  
    this.r = radius;  // The radius of the circle.  
}  
```  
  
 Při vyvolání konstruktoru Circle je třeba zadat hodnoty pro střed kruhu a poloměr. Nakonec získáte objekt Circle obsahující tři vlastnosti. Zde vidíte, jak byste měli vytvořit instanci objektu Circle.  
  
```JavaScript  
var aCircle = new Circle(5, 11, 99);  
```  
  
 Typ všechny objekty vytvářené pomocí vlastní konstruktor je `object`. Existuje pouze šest typů v jazyce JavaScript: `object`, `function`, `string`, `number`, `boolean`, a `undefined`. Další informace najdete v tématu [typeof – operátor](../../javascript/reference/typeof-operator-decrementjavascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Používání metody bind](../../javascript/advanced/using-the-bind-method-javascript.md)