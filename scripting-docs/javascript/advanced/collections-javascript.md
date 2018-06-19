---
title: Kolekce (JavaScript) | Microsoft Docs
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
ms.assetid: 23c26185-6a7b-4b69-9d22-63e1841b4905
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fab554f50f6d2fcdac92c562333e625dc0eb32f6
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
ms.locfileid: "27783049"
---
# <a name="collections-javascript"></a>Kolekce (JavaScript)
Můžete použít objekty kolekce [mapy](../../javascript/reference/map-object-javascript.md), [nastavit](../../javascript/reference/set-object-javascript.md), a [WeakMap](../../javascript/reference/weakmap-object-javascript.md) k ukládání hodnot a objekty. Tyto objekty poskytují vhodné metody pro přidávání a načítání členů pomocí klíče nebo hodnoty místo indexu. Chcete-li získat přístup k členům kolekce pomocí indexu, použijte `Array` objektu. Další informace najdete v tématu [pomocí pole](../../javascript/advanced/using-arrays-javascript.md).  
  
> [!CAUTION]
>  `Map`, `Set`, a `WeakMap` nejsou podporovány ve verzích prohlížeče před Internet Explorer 11. Další informace o podpoře verze najdete v tématu [informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="using-collections"></a>Používání kolekcí  
 `Map` a `WeakMap` objekty uložit dvojice klíč/hodnota a umožňují přidávat, načítat a odebírat členy pomocí klíče. Klíč a hodnota mohou být libovolného typu. `Set` Objekt ukládá hodnoty libovolného typu.  
  
 `Map` a `Set` objekty umožňují vytvořit výčet členů kolekce pomocí `forEach` metoda a zkontrolujte velikost kolekce pomocí `size` metoda. `WeakMap` Objekt, na rozdíl od není vyčíslitelná. Pro tuto kolekci jsou odkazy klíče uchovávány slabě. Použití `WeakMap` Pokud chcete, aby systém uvolňování k určení, zda se má zachovat každého člena kolekce v paměti aplikace. To může být užitečné například ve scénářích, kde jsou objekty uložené v mezipaměti velmi velké a nechcete zbytečně držet objekty v paměti. V některých scénářích můžete použít tento objekt k zamezení úniku informací z paměti.  
  
 Následující příklad ukazuje, jak používat `Map` objektu. V tomto příkladu jste přístup ke členům pomocí obou `get` a `forEach`. Funkce zpětného volání v `forEach` může trvat až tři parametry, které poskytují hodnota aktuálního elementu kolekce, klíč aktuálního elementu a samotného objektu kolekce.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
document.write(m.get(2));  
document.write("<br />");  
  
m.forEach(function (value, key, mapObj) {  
    document.write(value.toString() + "<br />");  
});  
  
// Output:  
// red  
  
// black  
// red  
// 2  
// 3  
  
```  
  
 Použití `WeakMap` je podobná `Map`kromě toho, že členové můžete načíst pouze pomocí `get`. Příklad, naleznete v části [WeakMap](../../javascript/reference/weakmap-object-javascript.md) objektu.  
  
 Následující příklad ukazuje, jak používat `Set` objektu. V tomto příkladu funkce zpětného volání přijímá jeden parametr, což je hodnota aktuálního prvku kolekce.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (value) {  
    document.write(value.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Pokročilé funkce jazyka JavaScript](../../javascript/advanced/advanced-javascript.md)