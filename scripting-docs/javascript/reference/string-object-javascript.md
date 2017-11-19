---
title: "String – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: String_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- String object
- String object, overview
ms.assetid: 8063ecd5-5778-4e87-b985-b21420171914
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d58f567bb301b29324fee8ed75fc95fd1a4791ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="string-object-javascript"></a>String – objekt (JavaScript)
Umožňuje manipulaci a formátování textových řetězců a určení a umístění podřetězců v řetězcích.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
newString = new String(["stringLiteral"])  
```  
  
## <a name="parameters"></a>Parametry  
 `newString`  
 Požadováno. Název proměnné, do kterého `String` objekt je přiřazen.  
  
 `stringLiteral`  
 Volitelné. Jakákoli skupina znaků Unicode.  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]poskytuje řídicí sekvence, které lze zahrnout v řetězcích vytvořit znaky, které nelze zadat přímo. Například `\t` určuje znaku tabulátoru. Další informace najdete v tématu [speciální znaky](../../javascript/advanced/special-characters-javascript.md).  
  
## <a name="string-literals"></a>Řetězcové literály  
 A *řetězcový literál* je nula nebo více znaků, které jsou v jednoduchých nebo dvojitých uvozovkách. Řetězcový literál má hlavní (primitivní) datový typ `string`. A *objektu řetězce* je vytvořená pomocí [operátor new](../../javascript/reference/new-operator-decrementjavascript.md), a má datový typ `Object`.  
  
 Následující příklad ukazuje, že datový typ řetězcový literál není stejný jako u `String` objektu.  
  
```JavaScript  
var strLit = "This is a string literal.";  
var strObj = new String("This is a string object.");  
  
document.write(typeof strLit);  
document.write("<br/>");  
document.write(typeof strObj);  
// Output:  
// string  
// object  
```  
  
## <a name="methods-for-string-literals"></a>Metody pro řetězcové literály  
 Řetězcový literál je při volání metody dočasně převeden na obálkový objekt string. Řetězcový literál považuje jako když `new` operátor jste použili k jeho vytvoření.  
  
 Následující příklad se vztahuje `toUpperCase` metodu pro řetězcový literál.  
  
```JavaScript  
var strLit = "This is a string literal.";  
  
var result1 = strLit.toUpperCase();  
  
var result2 = (new String(strLit)).toUpperCase();  
  
document.write(result1);  
document.write("<br/>");  
document.write(result2);  
// Output:   
// THIS IS A STRING LITERAL.  
// THIS IS A STRING LITERAL.  
```  
  
## <a name="accessing-an-individual-character"></a>Přístup k jednotlivým znakům  
 K jednotlivým znakům řetězce lze přistupovat jako k polem indexované vlastnosti dostupné pouze pro čtení. Tato funkce byla zavedena v [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)]. Následující příklad přistupuje k jednotlivým znakům řetězce.  
  
```JavaScript  
var str = "abcd";  
var result = str[2];  
document.write (result);  
// Output: c  
  
var result = "the"[0];  
document.write(result);  
// Output: t  
```  
  
## <a name="requirements"></a>Požadavky  
 `String Object` Byla zavedena v [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]. Některé členy v následujících seznamech byly zavedeny v pozdějších verzích.  
  
<a name="js56jsobjstringprop"></a>   
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `String` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-string.md)|Určuje funkci, která vytvoří objekt.|  
|[Length – vlastnost (String)](../../javascript/reference/length-property-string-javascript.md)|Vrátí délku `String` objektu.|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-string.md)|Vrátí odkaz na prototyp třídy objektů.|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `String` objektu.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[String.fromCharCode – funkce](../../javascript/reference/string-fromcharcode-function-javascript.md)|Vrátí hodnotu typu string z několika hodnot znaků Unicode.|  
|[String.fromcodepoint – funkce](../../javascript/reference/string-fromcodepoint-function-javascript.md)|Vrátí řetězec přidružený k bod kódu Unicode UTF-16.|  
|[String.RAW – funkce](../../javascript/reference/string-raw-function-javascript.md)|Vrátí Nezpracovaný řetězec formátu řetězec šablony.|  
  
<a name="js56jsobjstringmeth"></a>   
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `String` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Anchor – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí kolem textu ukotvovací značku jazyka HTML obsahující atribut NAME.|  
|[Big – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<BIG > značky kolem textu.|  
|[BLINK – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<BLINK > značky kolem textu.|  
|[Bold – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<B > značky kolem textu.|  
|[charAt – metoda](../../javascript/reference/charat-method-string-javascript.md)|Vrátí znak nacházející se na zadaném indexu.|  
|[charCodeAt – metoda](../../javascript/reference/charcodeat-method-string-javascript.md)|Vrátí kódování Unicode zadaného znaku.|  
|[codepointat – metoda](../../javascript/reference/codepointat-method-string-javascript.md)|Vrátí bod kódu pro znak Unicode UTF-16.|  
|[Metoda concat (řetězec)](../../javascript/reference/concat-method-string-javascript.md)|Vrátí řetězec, který obsahuje zřetězení dvou zadaných řetězců.|  
|[endsWith – metoda](../../javascript/reference/endswith-method-string-javascript.md)|Vrátí logickou hodnotu, která určuje, zda řetězec nebo dílčí řetězec končí předaný řetězec.|  
|[Includes – metoda](../../javascript/reference/includes-method-string-javascript.md)|Vrátí logickou hodnotu, která určuje, zda je předaný řetězec obsažené v objektu řetězce.|  
|[fixed – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<TT > značky kolem textu.|  
|[fontcolor – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<písma > značky s atributem barvu kolem textu.|  
|[FontSize – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<písma > značky s atributem velikost kolem textu.|  
|[hasOwnProperty – metoda](../../javascript/reference/hasownproperty-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda má objekt vlastnost se zadaným názvem.|  
|[Metoda indexOf (řetězec)](../../javascript/reference/indexof-method-string-javascript.md)|Vrátí pozici znaku, na které dojde k prvnímu výskytu podřetězce v řetězci.|  
|[isPrototypeOf – metoda](../../javascript/reference/isprototypeof-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda objekt existuje v řetězci prototypu jiného objektu.|  
|[italics – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<I > značky kolem textu.|  
|[Metoda lastIndexOf (řetězec)](../../javascript/reference/lastindexof-method-string-javascript.md)|Vrátí poslední výskyt podřetězce v řetězci.|  
|[odkaz – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí kolem textu ukotvovací značku jazyka HTML obsahující atribut HREF.|  
|[localeCompare – metoda](../../javascript/reference/localecompare-method-string-javascript.md)|Vrátí hodnotu, která označuje, zda jsou dva řetězce ekvivalentní v aktuálním národním prostředí.|  
|[Match – metoda](../../javascript/reference/match-method-string-javascript.md)|Vyhledá řetězec pomocí zadaný **regulární výraz** objektu a vrátí výsledky jako pole.|  
|[Normalize – metoda](../../javascript/reference/normalize-method-string-javascript.md)|Vrátí formu normalizace Unicode zadaného řetězce.|  
|[propertyIsEnumerable – metoda](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda zadaná vlastnost je součástí objektu a zda je vyčíslitelná.|  
|[REPEAT – metoda](../../javascript/reference/repeat-method-string-javascript.md)|Vrátí že nový objekt řetězce se hodnota rovná se původní řetězec opakuje zadaného počtu opakování.|  
|[replace – metoda](../../javascript/reference/replace-method-string-javascript.md)|Nahradí text v řetězci pomocí regulárního výrazu a vrátí výsledek.|  
|[Search – metoda](../../javascript/reference/search-method-string-javascript.md)|Vrátí pozici první shody podřetězce při vyhledávání regulárního výrazu.|  
|[Metoda slice (řetězec)](../../javascript/reference/slice-method-string-javascript.md)|Vrátí část řetězce.|  
|[Small – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<malé > značky kolem textu.|  
|[split – metoda](../../javascript/reference/split-method-string-javascript.md)|Vrátí pole řetězců, které vznikne rozdělením řetězce na podřetězce.|  
|[startsWith – metoda](../../javascript/reference/startswith-method-string-javascript.md)|Vrátí logickou hodnotu, která určuje, zda řetězec nebo dílčí řetězec začíná předaný řetězec.|  
|[Vytvořit – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<vytvořit > značky kolem textu.|  
|[Sub – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<SUB > značky kolem textu.|  
|[substr – metoda](../../javascript/reference/substr-method-string-javascript.md)|Vrátí počátek podřetězce dané délky na zadaném umístění.|  
|[substring – metoda](../../javascript/reference/substring-method-string-javascript.md)|Vrátí dílčí řetězec v určeném umístění v rámci `String` objektu.|  
|[sup – metoda](../../javascript/reference/html-tag-methods-javascript.md)|Umístí HTML \<SUP > značky kolem textu.|  
|[toLocaleLowerCase – metoda](../../javascript/reference/tolocalelowercase-method-string-javascript.md)|Vrátí hodnotu typu string, ve které jsou všechny znaky abecedy převedeny na malá písmena s přihlédnutím k aktuálnímu národnímu prostředí hostitele.|  
|[toLocaleString – metoda](../../javascript/reference/tolocalestring-method-object-javascript.md)|Vrátí objekt převedený na řetězec za použití aktuálního národního prostředí.|  
|[tolocaleuppercase – metoda](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)|Vrátí hodnotu typu string, ve které jsou všechny znaky abecedy převedeny na velká písmena s přihlédnutím k aktuálnímu národnímu prostředí hostitele.|  
|[toLowerCase – metoda](../../javascript/reference/tolowercase-method-javascript.md)|Vrátí hodnotu typu string, ve které jsou všechny znaky abecedy převedeny na malá písmena.|  
|[toString – metoda](../../javascript/reference/tostring-method-string-1.md)|Vrátí řetězec.|  
|[toUpperCase – metoda](../../javascript/reference/touppercase-method-string-javascript.md)|Vrátí hodnotu typu string, ve které jsou všechny znaky abecedy převedeny na velká písmena.|  
|[Trim – metoda](../../javascript/reference/trim-method-string-javascript.md)|Vrátí řetězec, z nějž byly odstraněny počáteční a koncové prázdné znaky a znaky zakončení řádku.|  
|[valueOf – metoda](../../javascript/reference/valueof-method-string.md)|Vrátí řetězec.|  
  
## <a name="see-also"></a>Viz také  
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Posouvání, posouvání a přibližování ukázkové aplikace](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)