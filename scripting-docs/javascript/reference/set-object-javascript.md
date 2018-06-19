---
title: Set – objekt (JavaScript) | Microsoft Docs
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
- Set
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4a4dd749-2a76-44fb-9cb0-a3ef317f75fb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5134ec09c9a8642499212af9dd5fd44de0068adc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791718"
---
# <a name="set-object-javascript"></a>Set – objekt (JavaScript)
Kolekce jedinečné hodnoty, které mohou být jakéhokoli typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
setObj = new Set()     
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud se pokusíte přidat jedinečný hodnota `Set`, nová hodnota nepřidají do kolekce.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Set` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Konstruktor](../../javascript/reference/constructor-property-set.md)|Určuje funkce, která vytvoří sadu.|  
|[prototyp](../../javascript/reference/prototype-property-set.md)|Vrátí odkaz na prototypu pro sadu.|  
|[velikost](../../javascript/reference/size-property-set-javascript.md)|Vrátí počet prvků v sadě.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Set` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Přidat](../../javascript/reference/add-method-set-javascript.md)|Přidá prvek na sadu.|  
|[Vymazat](../../javascript/reference/clear-method-set-javascript.md)|Odebere všechny elementy ze sady.|  
|[Odstranit](../../javascript/reference/delete-method-set-javascript.md)|Odebere zadaný element ze sady.|  
|[forEach](../../javascript/reference/foreach-method-set-javascript.md)|Provede zadanou akci pro každý prvek v sadě.|  
|[má](../../javascript/reference/has-method-set-javascript.md)|Vrátí `true` Pokud sada obsahuje zadaný element.|  
|[toString](../../javascript/reference/tostring-method-set-javascript.md)|Vrátí řetězcovou reprezentaci sady.|  
|[valueOf –](../../javascript/reference/valueof-method-set-javascript.md)|Vrátí primitivní hodnotu zadaného objektu.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidat členy do sady a potom je znovu načíst.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]