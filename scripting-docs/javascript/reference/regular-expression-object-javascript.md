---
title: "Objekt regulárního výrazu (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: RegularExpression_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Regular Expression object
- regular expressions, RegExp object
- RegExp object, overview
ms.assetid: 346aa83e-a045-47ea-acae-b42c7b121534
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df2d07e3b47e315ec804e5a7f20024dc2184eef0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="regular-expression-object-javascript"></a>Objekt regulárního výrazu (JavaScript)
Objekt, který obsahuje vzor regulárního výrazu společně s příznaky, které určují, jak se má použít vzor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
re = /pattern/[flags]  
```  
  
## <a name="syntax"></a>Syntaxe  
  
```  
re = new RegExp("pattern"[,"flags"])   
```  
  
## <a name="parameters"></a>Parametry  
 *Opětovná*  
 Požadováno. Název proměnné, ke kterému je přiřazena regulární výraz.  
  
 *vzor*  
 Požadováno. Vzor regulárního výrazu používat. Pokud chcete použít syntaxi 1, vymezení vzoru podle "/" znaků. Pokud chcete použít syntaxi 2, uzavřete vzoru v uvozovkách.  
  
 `flags`  
 Volitelné. Pokud použijete syntaxi 2, uzavřete příznak v uvozovkách. K dispozici příznaky, které mohou být spojeny, jsou:  
  
-   g (globální vyhledávání pro všechny výskyty *vzor*)  
  
-   i (ignorovat velká /)  
  
-   m (multiline vyhledávání)  
  
-   u (unicode), umožňuje EcmaScript 6 [funkce Unicode](../../javascript/advanced/special-characters-javascript.md). Podporováno pouze v [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)].  
  
-   Vyhledá y (trvalé odpovídají), shoduje se `lastIndex` vlastnost regulárního výrazu (a neprohledává na novější indexů). Podporované v [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)].  
  
## <a name="remarks"></a>Poznámky  
 **Regulární výraz** objekt Nezaměňovat s globální `RegExp` objektu. I když jejich zvukových stejná, budou samostatné a distinct. Vlastnosti **regulární výraz** objektu obsahují jenom informace o jeden konkrétní **regulární výraz** instance při vlastnosti na globální `RegExp` objekt obsahovat průběžně aktualizovat informace o každé shody, protože k ní dojde.  
  
 **Regulární výraz** objekty ukládání vzory použít při hledání řetězce pro kombinace znaků. Po **regulární výraz** je vytvořen objekt, je buď předaný metodě řetězci nebo jednu z metod regulární výraz je předán řetězec. Informace o poslední hledání provést jsou uloženy v globální `RegExp` objektu.  
  
 Použijte syntaxi 1, pokud víte, řetězec pro hledání dopředu. Použijte syntaxi 2, pokud řetězec pro hledání se často mění, nebo je neznámý, jako jsou třeba řetězce převzat ze vstupu uživatele.  
  
 *Vzor* argument zkompilován interní formát před použitím. Pro syntaxi 1 *vzor* je kompilovat, jako je skript načten. Syntaxi 2 *vzor* kompiluje těsně před použitím, nebo když **zkompilovat** metoda je volána.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **regulární výraz** objekt vytvořením objektu (re) obsahující vzor regulárního výrazu s jeho přidružené příznaky. V tomto případě výsledná **regulární výraz** objektu je následně používán `match` metoda:  
  
```JavaScript  
var s = "through the pages of the book";  
  
// Create regular expression pattern.  
var re = new RegExp("the", "i");  
  
// Attempt match on search string.  
var r = s.match(re);     
  
// Return first occurrence of "the".  
if(console && console.log) {  
    console.log(r);  
}  
  
// Output:  
//   
```  
  
## <a name="example"></a>Příklad  
 Následující příklad aktualizuje vzor regulárního výrazu pro hledání více instancí.  
  
```JavaScript  
// Create regular expression pattern using the i and g flags.  
var re = new RegExp("the", "ig");  
  
// Attempt match on search string.  
var r = s.match(re);     
  
// Return the two occurrences of "the".  
if(console && console.log) {  
    console.log(r.length);  
    console.log(r);  
}  
  
// Output:  
// 2  
// [object Array] ["the", "the"]  
```  
  
## <a name="example"></a>Příklad  
 Při použití příznak /y, je-li shoda úspěšné, aktualizuje `lastindex` indexu další znak po poslední shody. V případě selhání shody resetuje `lastindex` na hodnotu 0.  
  
 Následující příklad hledání shody v konkrétní indexu pomocí příznak /y a `lastIndex` vlastnost.  
  
```JavaScript  
// Create regular expression pattern using the i and y flags.  
var re = new RegExp("the", "iy");  
  
// Set the lastIndex property and attempt a match  
// at the specified index.  
re.lastIndex = 20;  
var r = s.match(re);     
  
// No matches returned.  
if(console && console.log) {  
    console.log(r);  
}  
// Reset the lastIndex property and attempt a match.  
re.lastIndex = 21;  
var r = s.match(re);  
  
// Return occurrence of "the" starting at index 21.  
if(console && console.log) {  
    console.log(r);  
}  
  
// Output:  
// null  
// [object Array] ["the"]  
```  
  
<a name="js56jsobjregexpressionprop"></a>   
## <a name="properties"></a>Vlastnosti  
 [globální vlastnost](../../javascript/reference/global-property-regular-expression-javascript.md) &#124; [IgnoreCase – vlastnost](../../javascript/reference/ignorecase-property-regular-expression-javascript.md) &#124; [multiline – vlastnost](../../javascript/reference/multiline-property-regular-expression-javascript.md) &#124; [source – vlastnost](../../javascript/reference/source-property-regular-expression-javascript.md)  
  
<a name="js56jsobjregexpressionmeth"></a>   
## <a name="methods"></a>Metody  
 [Compile – metoda](../../javascript/reference/compile-method-regular-expression-javascript.md) &#124; [exec metoda](../../javascript/reference/exec-method-regular-expression-javascript.md) &#124; [test – metoda](../../javascript/reference/test-method-regular-expression-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 U příznaku je podporována v [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)].  
  
 Příznak y je podporována v [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)