---
title: "JSON.Parse – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JSON.parse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parse JSON method
- JSON.parse method
ms.assetid: 20f00d31-5ab5-4c3c-ab49-2534fc39a9b4
caps.latest.revision: "41"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d66aee32a191c8cc1879c9436788c196c05e7bd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsonparse-function-javascript"></a>JSON.parse – funkce (JavaScript)
Převede řetězec formátu JavaScript Object Notation (JSON) na objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
JSON.parse(text [, reviver])  
```  
  
## <a name="parameters"></a>Parametry  
 `text`  
 Požadováno. Platný řetězec formátu JSON.  
  
 `reviver`  
 Volitelné. Funkce, která transformuje výsledky. Tato funkce je volána pro každý člen objektu. Obsahuje-li člen vnořené objekty, jsou tyto objekty převedeny dříve než nadřazený objekt. Pro každý člen nastanou následující události:  
  
-   Pokud `reviver` vrátí transformovanou hodnotu nahradí platnou hodnotu, hodnotu člena.  
  
-   Pokud `reviver` vrací stejnou hodnotu obdržel, hodnotu člena se nemění.  
  
-   Pokud `reviver` vrátí `null` nebo `undefined`, člen se odstraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Objekt nebo pole.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud způsobí, že tato funkce [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] chybě analyzátoru (například "SCRIPT1014: neplatný znak"), vstupního textu není v souladu s syntaxe JSON. Chcete-li chybu opravit, proveďte jednu z následujících akcí:  
  
-   Změnit `text` argument pro dosažení souladu s syntaxe JSON. Další informace najdete v tématu [zápis Syntaxe BNF](http://go.microsoft.com/fwlink/?LinkId=125203) objektů JSON.  
  
     Například, pokud odpověď je ve formátu JSONP místo čistého JSON, zkuste tento kód v objektu odpovědi:  
  
    ```JavaScript  
    var fixedResponse = response.responseText.replace(/\\'/g, "'");  
    var jsonObj = JSON.parse(fixedResponse);  
    ```  
  
-   Ujistěte se, že `text` argument byl serializován jako kompatibilní se standardem JSON implementací `JSON.stringify`.  
  
-   Spustit `text` argument ve validátoru JSON, jako [JSLint](http://www.jslint.com/) k identifikaci chyby syntaxe.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `JSON.parse` převést řetězec formátu JSON na objekt.  
  
```JavaScript  
var jsontext = '{"firstname":"Jesper","surname":"Aaberg","phone":["555-0100","555-0120"]}';  
var contact = JSON.parse(jsontext);  
document.write(contact.surname + ", " + contact.firstname);  
document.write(contact.phone[1]);  
// Output:  
// Aaberg, Jesper  
// 555-0100  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad převede pole na řetězec formátu JSON pomocí `JSON.stringify`a potom převede řetězec zpět na pole pomocí `JSON.parse`.  
  
```JavaScript  
var arr = ["a", "b", "c"];  
var str = JSON.stringify(arr);  
document.write(str);  
document.write ("<br/>");  
  
var newArr = JSON.parse(str);  
  
while (newArr.length > 0) {  
    document.write(newArr.pop() + "<br/>");  
}  
  
// Output:  
// ["a","b","c"]  
// c  
// b  
// a  
```  
  
## <a name="example"></a>Příklad  
 `reviver` Funkce se často používá k transformaci reprezentaci JSON mezinárodní organizace pro normalizaci (ISO) datum řetězce do formátu koordinovaný světový čas (UTC) `Date` objekty. Tento příklad používá `JSON.parse` k deserializaci řetězec ve formátu ISO datum. `dateReviver` Funkce vrátí `Date` objekty pro členy, kteří jsou formátovány jako ISO řetězce kalendářního data.  
  
```JavaScript  
var jsontext = '{ "hiredate": "2008-01-01T12:00:00Z", "birthdate": "2008-12-25T12:00:00Z" }';  
var dates = JSON.parse(jsontext, dateReviver);  
document.write(dates.birthdate.toUTCString());  
  
function dateReviver(key, value) {  
    var a;  
    if (typeof value === 'string') {  
        a = /^(\d{4})-(\d{2})-(\d{2})T(\d{2}):(\d{2}):(\d{2}(?:\.\d*)?)Z$/.exec(value);  
        if (a) {  
            return new Date(Date.UTC(+a[1], +a[2] - 1, +a[3], +a[4],  
                            +a[5], +a[6]));  
        }  
    }  
    return value;  
};  
  
// Output:  
// Thu, 25 Dec 2008 12:00:00 UTC  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [JSON.stringify – funkce](../../javascript/reference/json-stringify-function-javascript.md)   
 [tojson – metoda (Date)](../../javascript/reference/tojson-method-date-javascript.md)   
 [Centrum šablony ukázkovou aplikaci (pro Windows Store)](http://code.msdn.microsoft.com/Hub-template-sample-with-4b70002d)