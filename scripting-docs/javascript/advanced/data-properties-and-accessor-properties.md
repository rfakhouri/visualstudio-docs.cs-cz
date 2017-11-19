---
title: "Datové a přístupové vlastnosti | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 7e132831-375d-4728-9a57-5c6f91075b1c
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b800131ba76aa432492c0caefdbb9e8d5291924
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="data-properties-and-accessor-properties"></a>Vlastnosti dat a vlastnosti přístupového objektu
Tato část obsahuje všechny informace, které budete pravděpodobně potřebovat o datové a přístupové vlastnosti.  
  
### <a name="data-properties"></a>Vlastnosti dat  
 A *vlastnosti dat* je vlastnost, která můžete získat a nastavit hodnotu. Vlastnosti dat obsahovat `value` a `writable` vlastnosti v jejich popisovače.  
  
 Následující tabulka uvádí atributy pro vlastnost popisovač data.  
  
|Atribut popisovač dat|Popis|Výchozí|  
|-------------------------------|-----------------|-------------|  
|`value`|Aktuální hodnota vlastnosti.|`undefined`|  
|`writable`|`true`nebo `false`. Pokud `writable` je nastaven na `true`, hodnota vlastnosti je možné upravit.|`false`|  
|`enumerable`|`true`nebo `false`. Pokud `enumerable` je nastaven na `true`, může být ve výčtu vlastnosti `for...in` příkaz.|`false`|  
|`configurable`|`true`nebo `false`. Pokud `configurable` je nastaven na `true`, vlastnost atributy lze změnit, a vlastnost mohl být odstraněn.|`false`|  
  
 Pokud nemá popisovač `value`, `writable`, `get`, nebo `set` atribut a zadaný název vlastnosti neexistuje, bude přidána vlastnost data.  
  
 Když `configurable` atribut je `false` a `writable` je `true`, `value` a `writable` atributy lze změnit.  
  
#### <a name="data-properties-added-without-using-defineproperty"></a>Defineproperty – vlastnosti přidat bez použití dat  
 Pokud přidáte vlastnosti dat bez použití `Object.defineProperty`, `Object.defineProperties`, nebo `Object.create` funkce, `writable`, `enumerable`, a `configurable` atributy jsou nastaveny na `true`. Po přidání vlastnost, můžete ji upravit pomocí `Object.defineProperty` funkce.  
  
 Můžete použít tyto způsoby přidání vlastnosti dat:  
  
-   Operátor přiřazení (=), jako v`obj.color = "white";`  
  
-   Literálu, jako v objektu`obj = { color: "white", height: 5 };`  
  
-   Funkce vytváření, jak je popsáno v [pomocí konstruktorů definovat typy](../../javascript/advanced/using-constructors-to-define-types.md)  
  
### <a name="accessor-properties"></a>Přistupující objekt vlastnosti  
 *Přistupujícího objektu vlastnosti* volá funkci zadaný uživatelem pokaždé, když je hodnota vlastnosti nastavit nebo načíst. Popisovač přistupujícího objektu vlastnosti obsahuje `get` atribut `set` atribut, nebo obojí.  
  
 Následující tabulka obsahuje seznam atributy pro popisovač přistupujícího objektu vlastnosti.  
  
|Atribut popisovač přistupujícího objektu|Popis|Výchozí|  
|-----------------------------------|-----------------|-------------|  
|`get`|Funkce, která vrátí hodnotu vlastnosti. Funkce nemá žádné parametry.|`undefined`|  
|`set`|Funkce, která nastaví hodnotu vlastnosti. Má jeden parametr, který obsahuje hodnotu pro přiřazení.|`undefined`|  
|`enumerable`|`true`nebo `false`. Pokud `enumerable` je nastaven na `true`, může být ve výčtu vlastnosti `for...in` příkaz.|`false`|  
|`configurable`|`true`nebo `false`. Pokud `configurable` je nastaven na `true`, vlastnost atributy lze změnit, a vlastnost mohl být odstraněn.|`false`|  
  
 Když `get` přistupujícího objektu není definován a je proveden pokus o přístup k vlastnosti hodnotu, je hodnota `undefined` je vrácen. Když `set` přistupujícího objektu není definován a je proveden pokus o o přiřazení hodnoty k vlastnosti přístupového objektu, nedojde k žádné akci.  
  
### <a name="property-modifications"></a>Úpravy vlastností  
 Pokud objekt již má vlastnost se zadaným názvem, jsou upravit atributy vlastnost. Když upravíte vlastnosti, atributy, které nebyly zadány v popisovači zůstávají stejné.  
  
 Pokud `configurable` atribut existující vlastnost je `false`, pouze povolené, změna se mění `writable` atribut z `true` k `false`.  
  
 Vlastnost dat můžete změnit na přistupujícího objektu vlastnosti a naopak. Pokud to `configurable` a `enumerable` atributy, které nebyly zadány v popisovači zachovány ve vlastnosti. Ostatní atributy, které nejsou v popisovači jsou nastavené na výchozí hodnoty.  
  
 Konfigurovat přistupujícího objektu vlastnosti můžete definovat přírůstkově pomocí více volání `Object.defineProperty` funkce. Například jeden `Object.defineProperty` volání mohou definovat pouze `get` přistupujícího objektu. Může definovat novější volání na stejný název vlastnosti `set` přistupujícího objektu. Vlastnost by pak znamenalo i `get` přistupujícího objektu a `set` přistupujícího objektu.  
  
 Chcete-li získat popisovač objektu, který se vztahuje na existuje vlastnost, můžete použít [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
 Můžete použít [Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md) a [Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md) aby se zabránilo změně vlastnost atributy.