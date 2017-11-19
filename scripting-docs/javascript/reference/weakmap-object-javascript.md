---
title: "Weakmap – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: WeakMap
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4682d2dc-caf9-4fa8-8313-a0a0b804fd1d
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8de97f8acb94921090696e9019a1df5d945db7c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="weakmap-object-javascript"></a>WeakMap – objekt (JavaScript)
Kolekce dvojic klíč/hodnota, ve kterých každý klíč je odkaz na objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
weakmapObj = new WeakMap()  
```  
  
## <a name="remarks"></a>Poznámky  
 A `WeakMap` objektu není možné provést výčet.  
  
 Pokud přidáte do kolekce pomocí existujícího klíče hodnotu, nová hodnota nahradí původní hodnoty.  
  
 V `WeakMap` objektu, odkazy na objekty klíče jsou uložené 'slabě'. To znamená, že `WeakMap` nezabrání uvolňování nedocházelo na objekty klíče. Pokud nejsou žádné odkazy (jiné než `WeakMap`) pro objekty klíče, bude systém uvolňování může shromažďovat klíče objekty.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `WeakMap` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Konstruktor](../../javascript/reference/constructor-property-weakmap.md)|Určuje funkce, která vytvoří `WeakMap`.|  
|[prototyp](../../javascript/reference/prototype-property-weakmap.md)|Vrátí odkaz na prototypu pro `WeakMap`.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `WeakMap` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Vymazat](../../javascript/reference/clear-method-weakmap-javascript.md)|Odebere všechny elementy z `WeakMap`.|  
|[Odstranit](../../javascript/reference/delete-method-weakmap-javascript.md)|Odebere zadaný element z `WeakMap`.|  
|[GET](../../javascript/reference/get-method-weakmap-javascript.md)|Vrátí zadaný element z `WeakMap`.|  
|[má](../../javascript/reference/has-method-weakmap-javascript.md)|Vrátí `true` Pokud `WeakMap` obsahuje zadaný element.|  
|[nastavení](../../javascript/reference/set-method-weakmap-javascript.md)|Přidá nového elementu `WeakMap`.|  
|[toString](../../javascript/reference/tostring-method-weakmap-javascript.md)|Vrátí řetězcovou reprezentaci `WeakMap`.|  
|[valueOf –](../../javascript/reference/valueof-method-weakmap-javascript.md)|Vrátí primitivní hodnotu zadaného objektu.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `WeakMap` objekt a potom je znovu načíst.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
  
document.write(wm.get(dog) + ": ");  
document.write(dog.breed);  
document.write("<br />");  
document.write(wm.get(cat) + ": ");  
document.write(cat.breed);  
  
// Output:  
// fido: yorkie  
// pepper: burmese  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]