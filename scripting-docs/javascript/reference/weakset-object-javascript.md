---
title: "Weakset – objekt (JavaScript) | Microsoft Docs"
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
ms.assetid: f97e6e7c-d678-4e32-978e-d949a7cafa3a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e42849c03f698d6ed5f8b0e28725c85555a74d2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="weakset-object-javascript"></a>WeakSet – objekt (JavaScript)
Kolekce jedinečný objekty, které mohou být jakéhokoli typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
setObj = new WeakSet()  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud se pokusíte přidat do objekt jedinečný `WeakSet`, nový objekt nepřidají do kolekce.  
  
 Na rozdíl od `Set`, pouze objekty mohou být přidány do kolekce. Libovolné hodnoty nelze přidat do kolekce.  
  
 V `WeakSet` objektu, odkazy na objekty v sadě jsou uložené 'slabě'. To znamená, že `WeakSet` nezabrání uvolňování nedocházelo na objektech. Pokud nejsou žádné odkazy (jiné než `WeakSet`) k objektům, může shromažďovat uvolňování objektů.  
  
 `WeakSet`(nebo `WeakMap`) může být užitečné v některých scénářích zahrnující ukládání do mezipaměti objektů nebo objekt metadat. Například metadata pro jiné rozšiřitelné objekty mohou být uloženy v `WeakSet`, nebo můžete vytvořit mezipaměť obrázky uživatele pomocí `WeakSet`.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `WeakSet` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|– konstruktor|Určuje funkce, která vytvoří sadu.|  
|prototyp|Vrátí odkaz na prototypu pro sadu.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `WeakSet` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|add|Přidá prvek na sadu.|  
|Odstranit|Odebere zadaný element ze sady.|  
|má|Vrátí `true` Pokud sada obsahuje zadaný element.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidat členy do sady a potom ověřte, že byly přidány.  
  
```JavaScript  
var ws = new WeakSet();  
  
var str = new String("Thomas Jefferson");  
var num = new Number(1776);  
  
ws.add(str);  
ws.add(num);  
  
console.log(ws.has(str));  
console.log(ws.has(num));  
  
ws.delete(str);  
console.log(ws.has(str));  
  
// Output:  
// true  
// true  
// false  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]