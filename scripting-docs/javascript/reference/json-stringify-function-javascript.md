---
title: JSON.stringify – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- stringify method
ms.assetid: 0fafaf3b-c29b-46dc-b65b-ca223064a1d0
caps.latest.revision: 40
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3539bb003ed20a3ff7586e42466bf7c47165b83f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791676"
---
# <a name="jsonstringify-function-javascript"></a>JSON.stringify – funkce (JavaScript)
Převede [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu řetězce JavaScript Object Notation (JSON).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
JSON.stringify(  
value [, replacer] [, space])  
```  
  
## <a name="parameters"></a>Parametry  
 `value`  
 Požadováno. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu, obvykle na objekt nebo pole, které má být převeden.  
  
 `replacer`  
 Volitelné. Funkce nebo pole transformující výsledky.  
  
 Pokud `replacer` je funkce, `JSON.stringify` volá funkci předávání v klíče a hodnoty u každého člena. Místo původní hodnoty se použije návratová hodnota. Pokud funkce vrátí `undefined`, člen je vyloučen. Klíč pro kořenový objekt je prázdný řetězec: "".  
  
 Pokud `replacer` je pole, pouze členové s klíčem hodnoty v poli, bude převeden. Pořadí, ve kterém jsou členy převedeny, je stejné jako pořadí klíčů v poli. `replacer` Pole se ignoruje při `value` argument je také pole.  
  
 `space`  
 Volitelné. Přidá k textu návratové hodnoty JSON odsazení, mezeru a znaky konce řádku, aby bylo jeho čtení snazší.  
  
 Pokud `space` je tento parametr vynechán, vrátí hodnotu text se vygeneruje bez veškeré místo navíc prázdné.  
  
 Pokud `space` číslo, vrátí hodnotu text odsazeno s zadaný počet mezer na každé úrovni. Pokud `space` je větší než 10, je text zobrazují odsazené prostorů 10.  
  
 Pokud `space` je řetězec prázdný, jako je například '\t' text vrátit hodnotu odsazeno s znaky v řetězci na každé úrovni.  
  
 Pokud `space` je řetězec, který je delší než 10 znaků, se používají prvních 10 znaků.  
  
## <a name="return-value"></a>Návratová hodnota  
 Řetězec obsahující text JSON.  
  
## <a name="exceptions"></a>Výjimky  
  
|Výjimka|Podmínka|  
|---------------|---------------|  
|[Neplatný argument nahrazení](../../javascript/misc/invalid-replacer-argument.md)|`replacer` Argument není funkce nebo pole.|  
|[Cyklický odkaz v argumentu hodnoty není podporován](../../javascript/misc/circular-reference-in-value-argument-not-supported.md)|`value` Argument obsahuje cyklický odkaz.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud `value` má `toJSON` metody `JSON.stringify` funkce používá návratovou hodnotu této metody. Pokud vrátí hodnotu, která `toJSON` je metoda `undefined`, člen není převést. To umožňuje objektu určit jeho vlastní reprezentaci JSON.  
  
 Hodnoty, které nemají reprezentace JSON, jako například `undefined`, nebudete převádět. V objektech budou zahozeny. V polích budou nahrazeny hodnotou null.  
  
 Hodnoty řetězce začínají a končí uvozovkami. Všechny znaky Unicode mohou být uzavřeny v uvozovkách, s výjimkou znaků, které musejí být uvozeny pomocí zpětného lomítka. Následujícím znakům musí předcházet zpětné lomítko:  
  
-   Uvozovky (")  
  
-   Zpětné lomítko (\\)  
  
-   Backspace (b)  
  
-   Formfeed (f)  
  
-   Nový řádek (n)  
  
-   návrat na začátek řádku (r)  
  
-   Horizontální tabulátor (t)  
  
-   Čtyři šestnáctkové číslice (uhhhh)  
  
## <a name="order-of-execution"></a>Pořadí spouštění  
 Během serializace Pokud `toJSON` metoda existuje pro `value` argument, `JSON.stringify` nejprve volá `toJSON` metoda. Pokud neexistuje, je použita původní hodnota. Další, pokud `replacer` argumentu k dispozici, hodnota (původní hodnotu nebo `toJSON` vrátit hodnotu) se nahradí vrátit hodnota `replacer` argument. Nakonec se přidají prázdné znaky na hodnotu podle volitelné `space` argument ke generování konečné text JSON.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `JSON.stringify` převést `contact` objekt, který chcete JSON text. `memberfilter` Pole je definován tak pouze `surname` a `phone` se převedou členy. `firstname` Člen je vynechán.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Array();  
memberfilter[0] = "surname";  
memberfilter[1] = "phone";  
var jsonText = JSON.stringify(contact, memberfilter, "\t");  
document.write(jsonText);  
// Output:   
// { "surname": "Aaberg", "phone": [ "555-0100", "555-0120" ] }  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `JSON.stringify` s pole. `replaceToUpper` Funkce převede každý řetězec v poli na velká písmena.  
  
```JavaScript  
var continents = new Array();  
continents[0] = "Europe";  
continents[1] = "Asia";  
continents[2] = "Australia";  
continents[3] = "Antarctica";  
continents[4] = "North America";  
continents[5] = "South America";  
continents[6] = "Africa";  
  
var jsonText = JSON.stringify(continents, replaceToUpper);  
  
function replaceToUpper(key, value) {  
    return value.toString().toUpperCase();  
}  
  
//Output:  
// "EUROPE,ASIA,AUSTRALIA,ANTARCTICA,NORTH AMERICA,SOUTH AMERICA,AFRICA"  
  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `toJSON` způsobů, jak převést řetězcové hodnoty na velká písmena.  
  
```JavaScript  
var contact = new Object();   
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
document.write(jsonText);  
  
// Output:  
{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}  
  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [JSON.Parse – funkce](../../javascript/reference/json-parse-function-javascript.md)   
 [tojson – metoda (Date)](../../javascript/reference/tojson-method-date-javascript.md)   
 [Informačního kanálu čtečky ukázkovou aplikaci (pro Windows Store)](http://code.msdn.microsoft.com/Feed-reader-sample-99d68cf8)