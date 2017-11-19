---
title: "Array – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Array
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Array object
- constructor property
ms.assetid: 08e5f552-0797-4b48-8164-609582fc18c9
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a48d0ab5bac9d532e8fe8e356f4ea4df9e377b02
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="array-object-javascript"></a>Array – objekt (JavaScript)
Poskytuje podporu pro vytváření polí libovolného datového typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```
arrayObj = new Array()  
arrayObj = new Array([size])  
arrayObj = new Array([element0[, element1[, ...[, elementN]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. Název proměnné, do kterého `Array` objekt je přiřazen.  
  
 `size`  
 Volitelné. Velikost pole. Pole jsou od nuly, vytvořené prvky budou mít indexy od nuly do `size` -1.  
  
 `element0,...,elementN`  
 Volitelné. Prvky, které mají být umístěny do pole. Tím se vytvoří pole s  *n*  + 1 elementy a `length` z  *n*  + 1. Při použití této syntaxe je zapotřebí poskytnout více než jeden prvek.  
  
## <a name="remarks"></a>Poznámky  
 Po vytvoření pole lze k jednotlivým prvkům pole přistupovat pomocí zápisu [ ]. Všimněte si, že maticových v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] jsou od nuly.  
  
```JavaScript  
var my_array = new Array();  
for (i = 0; i < 10; i++) {  
    my_array[i] = i;  
}  
x = my_array[4];  
document.write(x);  
  
// Output: 4  
```  
  
 Můžete předat celé číslo bez znaménka 32-bit do `Array` konstruktor možné určit velikost pole. Je-li hodnota záporná nebo není-li typu integer, dojde k chybě za běhu aplikace. Spuštění následujícího kódu by tuto chybu mělo zobrazit v konzole.  
  
```JavaScript  
var arr = new Array(10);  
document.write(arr.length);  
  
// Output: 10  
  
// Don't do this  
var arr = new Array(-1);  
arr = new Array(1.50);   
```  
  
 Pokud je předán jednu hodnotu `Array` konstruktor ale není číslo, `length` je nastavena na hodnotu 1 a hodnota jediným prvkem stane jeden, předaný argument.  
  
```npl  
var arr = new Array("one");  
document.write(arr.length);  
document.write("<br/>");  
document.write(arr[0]);  
  
// Output:  
1  
one  
  
```  
  
 Pole jazyka JavaScript jsou řídká pole, což znamená, že ne všechny prvky pole musí obsahovat data. V jazyce JavaScript existují v poli pouze prvky, které skutečně obsahují data. Tím je sníženo množství paměti využité polem.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 Některé členy v následujících seznamech byly zavedeny v pozdějších verzích. Další informace najdete v tématu [informace o verzi](../../javascript/reference/javascript-version-information.md) nebo v dokumentaci pro jednotlivé členy.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Array` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-array.md)|Určuje funkci, která vytvoří pole.|  
|[Length – vlastnost (pole)](../../javascript/reference/length-property-array-javascript.md)|Vrátí celočíselnou hodnotu o 1 vyšší než nejvyšší prvek definovaný v poli.|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-array.md)|Vrátí odkaz na prototyp pole.|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka popisuje funkcí `Array` objektu.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[Array.from – funkce](../../javascript/reference/array-from-function-array-javascript.md)|Vrátí pole z objektu jako pole nebo iterable.|  
|[Array.IsArray – funkce](../../javascript/reference/array-isarray-function-javascript.md)|Vrátí logickou hodnotu, která označuje, zda je objekt pole.|  
|[Array.of – funkce](../../javascript/reference/array-of-function-array-javascript.md)|Vrátí pole z předané argumenty.|  
  
<a name="js56jsobjarraymeth"></a>   
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Array` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Metoda concat (pole)](../../javascript/reference/concat-method-array-javascript.md)|Vrátí nové pole sestávající z kombinace dvou polí.|  
|[Entries – metoda](../../javascript/reference/entries-method-array-javascript.md)|Vrátí iterátor, který obsahuje dvojice klíč/hodnota pole.|  
|[EVERY – metoda](../../javascript/reference/every-method-array-javascript.md)|Kontroluje, zda funkce zpětného volání definovaného vrátí `true` pro všechny elementy v matici.|  
|[Fill – metoda](../../javascript/reference/fill-method-array-javascript.md)|Naplní pole se zadanou hodnotou.|  
|[Filter – metoda](../../javascript/reference/filter-method-array-javascript.md)|Volá funkci zpětného volání definovaného pro každý element pole a vrátí pole hodnot, pro které se vrátí funkce zpětného volání `true`.|  
|[findIndex – metoda](../../javascript/reference/findindex-method-array-javascript.md)|Vrátí hodnotu indexu pro první prvek pole, že splňuje test kritéria zadaná ve funkci zpětného volání.|  
|[foreach – metoda](../../javascript/reference/foreach-method-array-javascript.md)|Volá definovanou funkci zpětného volání pro každý prvek v poli.|  
|[hasOwnProperty – metoda](../../javascript/reference/hasownproperty-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda má objekt vlastnost se zadaným názvem.|  
|[Metoda indexOf (pole)](../../javascript/reference/indexof-method-array-javascript.md)|Vrátí index prvního výskytu hodnoty v poli.|  
|[isPrototypeOf – metoda](../../javascript/reference/isprototypeof-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda objekt existuje v řetězci prototypu jiného objektu.|  
|[JOIN – metoda](../../javascript/reference/join-method-array-javascript.md)|Vrátí `String` objekt, který se skládá z všechny elementy pole zřetězen dohromady.|  
|[Keys – metoda](../../javascript/reference/keys-method-array-javascript.md)|Vrátí iterátor, který obsahuje hodnoty indexu pole.|  
|[Metoda lastIndexOf (pole)](../../javascript/reference/lastindexof-method-array-javascript.md)|Vrátí index posledního výskytu zadané hodnoty v poli.|  
|[map – metoda](../../javascript/reference/map-method-array-javascript.md)|Volá definovanou funkci zpětného volání na každý prvek pole a vrátí pole obsahující výsledky.|  
|[POP – metoda](../../javascript/reference/pop-method-array-javascript.md)|Odstraní poslední prvek z pole a vrátí jej.|  
|[propertyIsEnumerable – metoda](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda zadaná vlastnost je součástí objektu a zda je vyčíslitelná.|  
|[push – metoda](../../javascript/reference/push-method-array-javascript.md)|Přidá do pole nové prvky a vrátí novou velikost pole.|  
|[reduce – metoda](../../javascript/reference/reduce-method-array-javascript.md)|Nahromadí jediný výsledek voláním definované funkce zpětného volání pro všechny prvky v poli. Vrácená hodnota funkce zpětného volání je akumulovaný výsledek poskytnutý jako argument v dalším volání funkce zpětného volání.|  
|[reduceright – metoda](../../javascript/reference/reduceright-method-array-javascript.md)|Nahromadí jediný výsledek voláním definované funkce zpětného volání pro všechny prvky v poli v sestupném pořadí. Vrácená hodnota funkce zpětného volání je akumulovaný výsledek poskytnutý jako argument v dalším volání funkce zpětného volání.|  
|[Reverse – metoda](../../javascript/reference/reverse-method-javascript.md)|Vrátí `Array` vrátit objekt s elementy.|  
|[SHIFT – metoda](../../javascript/reference/shift-method-array-javascript.md)|Odstraní první prvek z pole a vrátí jej.|  
|[Metoda slice (pole)](../../javascript/reference/slice-method-array-javascript.md)|Vrátí část pole.|  
|[SOME – metoda](../../javascript/reference/some-method-array-javascript.md)|Kontroluje, zda funkce zpětného volání definovaného vrátí `true` pro libovolný element pole.|  
|[sort – metoda](../../javascript/reference/sort-method-array-javascript.md)|Vrátí `Array` objekt s elementy seřazeny.|  
|[splice – metoda](../../javascript/reference/splice-method-array-javascript.md)|Odstraní prvky z pole, v případě potřeby vloží na jejich místo nové prvky a vrátí odstraněné prvky.|  
|[toLocaleString – metoda](../../javascript/reference/tolocalestring-method-object-javascript.md)|Vrátí řetězec za použití aktuálního národního prostředí.|  
|[toString – metoda](../../javascript/reference/tostring-method-array.md)|Vrátí řetězcovou reprezentaci pole.|  
|[unshift – metoda](../../javascript/reference/unshift-method-array-javascript.md)|Vloží nové prvky na začátek pole.|  
|[valueOf – metoda](../../javascript/reference/valueof-method-array.md)|Načte odkaz na pole.|  
|[Values – metoda](../../javascript/reference/values-method-array-javascript.md)|Vrátí iterátor, který obsahuje hodnoty pole.|  
  
## <a name="see-also"></a>Viz také  
 [Posouvání, posouvání a přibližování ukázkové aplikace](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)