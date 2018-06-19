---
title: Map – objekt (JavaScript) | Microsoft Docs
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
- Map
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a91dbcbe-f58d-41a0-be15-8c9d30020327
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d89890f9fecaf61e47e136734ed7fefb7b73cabd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791295"
---
# <a name="map-object-javascript"></a>Map – objekt (JavaScript)
Kolekce dvojic klíč/hodnota.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
mapObj = new Map()  
```  
  
## <a name="remarks"></a>Poznámky  
 Klíče a hodnoty v kolekci může být jakéhokoli typu. Pokud přidáte do kolekce pomocí existujícího klíče hodnotu, nová hodnota nahradí původní hodnoty.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Map` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Konstruktor](../../javascript/reference/constructor-property-map.md)|Určuje funkce, která vytváří mapu.|  
|[prototyp](../../javascript/reference/prototype-property-map.md)|Vrátí odkaz na prototypu pro mapu.|  
|[velikost](../../javascript/reference/size-property-map-javascript.md)|Vrátí počet prvků v mapování.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Map` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Vymazat](../../javascript/reference/clear-method-map-javascript.md)|Odebere všechny elementy mapy.|  
|[Odstranit](../../javascript/reference/delete-method-map-javascript.md)|Odebere zadaný element mapy.|  
|[forEach](../../javascript/reference/foreach-method-map-javascript.md)|Provede zadanou akci pro každý prvek v mapování.|  
|[GET](../../javascript/reference/get-method-map-javascript.md)|Vrátí zadaný element z mapy.|  
|[má](../../javascript/reference/has-method-map-javascript.md)|Vrátí `true` Pokud mapy obsahuje zadaný element.|  
|[nastavení](../../javascript/reference/set-method-map-javascript.md)|Přidá nového elementu mapy.|  
|[toString](../../javascript/reference/tostring-method-map-javascript.md)|Vrátí řetězcovou reprezentaci mapy.|  
|[valueOf –](../../javascript/reference/valueof-method-map-javascript.md)|Vrátí primitivní hodnotu zadaného objektu.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `Map` a potom je znovu načíst.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (item, key, mapObj) {  
    document.write(item.toString() + "<br />");  
});  
  
document.write("<br />");  
document.write(m.get(2));  
  
// Output:  
// black  
// red  
// 2  
// 3  
//  
// red  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]