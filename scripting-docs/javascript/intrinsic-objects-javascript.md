---
title: Vnitřní objekty (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- built-in objects [JavaScript]
- intrinsic objects [JavaScript]
ms.assetid: 6520c634-a7d1-4a05-8c1b-2e79f449d2e4
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 242b572c2818f9968e6d5fc51e1272e3004c0f05
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789273"
---
# <a name="intrinsic-objects-javascript"></a>Vnitřní objekty (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]poskytuje objekty vnitřní (a "integrované"). Jsou `Array`, `Boolean`, `Date`, `Error`, `Function`, **globální**, **JSON**, **matematické**,  **Číslo**, `Object`, `RegExp`, a `String` objekty. Vnitřní objekty přidruženými metody, funkce, vlastnosti a konstanty, které jsou podrobně popsány v [referenční příručka jazyka](../javascript/reference/javascript-reference.md).  
  
## <a name="array-object"></a>Objekt Array  
 Dolní indexy pole lze chápat jako vlastnosti objektu a jsou uvedené podle jejich číselného indexu. Všimněte si, že s názvem vlastnosti, které jsou přidány do pole nelze indexovat pomocí čísla. jsou oddělené od prvků pole.  
  
 Chcete-li vytvořit nové pole, použijte **nové** operátor a **Array()** [konstruktor](../javascript/reference/constructor-property-object-javascript.md), jako v následujícím příkladu.  
  
```JavaScript  
var theMonths = new Array(12);  
theMonths[0] = "Jan";  
theMonths[1] = "Feb";  
theMonths[2] = "Mar";  
theMonths[3] = "Apr";  
theMonths[4] = "May";  
theMonths[5] = "Jun";  
theMonths[6] = "Jul";  
theMonths[7] = "Aug";  
theMonths[8] = "Sep";  
theMonths[9] = "Oct";  
theMonths[10] = "Nov";  
theMonths[11] = "Dec";  
```  
  
 Při vytváření pole pomocí `Array` – klíčové slovo, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] zahrnuje **délka** vlastnosti, která zaznamenává počet položek. Pokud nezadáte číslo, délka nastavena na 0 a pole nemá žádné položky. Pokud zadáte číslo, délka nastavena na toto číslo. Pokud zadáte více než jeden parametr, parametry slouží jako položky v poli. Počet parametrů je kromě toho přiřadit k vlastnosti délka, jako v následujícím příkladu, který je ekvivalentní v předchozím příkladu.  
  
```JavaScript  
var theMonths = new Array("Jan", "Feb", "Mar", "Apr", "May", "Jun",   
"Jul", "Aug", "Sep", "Oct", "Nov", "Dec");  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]automaticky změní hodnotu **délka** při přidávání elementů do pole, které jste vytvořili pomocí `Array` – klíčové slovo. Pole indexů v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] vždy začínají 0, 1, není proto vlastnost délka je vždy jeden znak větší než největší index v poli.  
  
## <a name="string-object"></a>Objekt String  
 V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], jako kdyby byly objekty lze považovat řetězce (a čísla). [Řetězec objekt](../javascript/reference/string-object-javascript.md) má určitá předdefinované metody, které můžete použít s vaší řetězce. Jedním z nich je [substring – metoda](../javascript/reference/substring-method-string-javascript.md), která vrací součást řetězce identifikátoru. Jako argumenty trvá dvou čísel.  
  
```JavaScript  
var aString = "0123456789";  
  
// This code sets aChunk to "456".  
var aChunk = aString.substring(4, 7);  
  
// This code sets anotherChunk to "456", using  
// the lower value index as the starting index.  
var anotherChunk = aString.substring(7, 4);  
  
// This code sets the firstLetter variable to "J"  
// by using the array in the preceding array creation example.  
firstLetter = theMonths[5].substring(0,1);  
```  
  
 Jiné vlastnosti `String` objekt je **délka** vlastnost. Tato vlastnost obsahuje počet znaků v řetězci (0 pro prázdný řetězec). Tato číselnou hodnotu a je možné přímo ve výpočtech.  
  
```JavaScript  
var howLong = "Hello World".length  // Sets the howLong variable to 11.  
```  
  
## <a name="math-object"></a>Objekt Math  
 **Matematické** objekt má několik předdefinovaných konstanty a funkce. Konstanty jsou konkrétní čísla. Jedním z těchto konkrétních čísla je hodnotu čísla pí (přibližně 3,14159...). Toto je **Math.PI** konstantní, uvedené v následujícím příkladu.  
  
```JavaScript  
var radius = 5;  
var circleArea = Math.PI * radius * radius;  
```  
  
 Jeden z předdefinovaných funkcí **matematické** objekt je v případě metody exponenciální zápis nebo `Math.pow`, která Umocní jedno číslo na zadanou mocninu. Následující příklad používá k výpočtu svazku oblasti platformy a exponenciální zápis.  
  
```JavaScript  
var volume = (4/3)*(Math.PI*Math.pow(radius,3));  
```  
  
## <a name="date-object"></a>Objekt Date  
 `Date` Objekt lze použít k reprezentování libovolný data a časy, chcete-li získat aktuální systémový datum a k výpočtu rozdíly mezi daty. Má několik vlastností a metod, všechny předdefinované. Obecně `Date` objekt poskytuje den v týdnu; měsíc, den a rok; a doba v hodinách, minuty a sekundy. Tyto informace je založena na počet milisekund od 1. ledna 1970 GMT 00:00:00.000, což je greenwichský střední čas (Upřednostňovaný termín je UTC, nebo "Světového koordinovaného času,", který odkazuje na signály vystavený standardní čas World). [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]dokáže zpracovat kalendářních dat, které jsou v rozsahu přibližnou př.n.l 250 000. k 255,000 roku.  
  
 Chcete-li vytvořit novou `Date` objektu, použijte **nové** operátor, jak je znázorněno v následujícím příkladu.  
  
```JavaScript  
var toDay = new Date();    
var thisYear = toDay.getFullYear();  
var thisMonth = theMonths[toDay.getMonth()];  
var thisDay = thisMonth  + " " + toDay.getDate() + ", " + thisYear;  
```  
  
## <a name="number-object"></a>Objekt Number  
 Kromě speciální číselné konstanty (`PI`, například), jsou k dispozici v **matematické** objekt, jsou k dispozici v několika dalších konstanty [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] prostřednictvím **číslo** objekt.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|Number.MAX_VALUE|Maximální možný počet, o 1, 79E + 308; může být kladná nebo záporná. (Hodnota se liší systémy mírně.)|  
|Number.MIN_VALUE|Nejmenší možný počet, o 5.00E-324; může být kladná nebo záporná. (Hodnota se liší systémy mírně.)|  
|Number.NaN|Speciální číselného typu hodnotu "není číslo."|  
|Number.positive_infinity –|Všechny kladná hodnota větší než největší kladné číslo (Number.MAX_VALUE) je automaticky převeden na tuto hodnotu; reprezentován jako nekonečna.|  
|Number.negative_infinity –|Libovolná hodnota záporná více než největší záporné číslo (-Number.MAX_VALUE) je automaticky převeden na tuto hodnotu; vyjádřené - infinity.|  
  
 **Number.NaN** je speciální konstanta, která je definována jako "není číslo." Pokus o analyzovat řetězec, který nelze analyzovat jako číslo vrátí **Number.NaN**. `NaN`Porovná nerovné na libovolné číslo a na sebe sama. Chcete otestovat `NaN` dojít, není porovnán **Number.NaN**; použít **isNaN()** funkce místo.  
  
## <a name="json-object"></a>Objekt JSON  
 JSON je prostý výměnu dat formát založený na podmnožinu literálu zápis objektů jazyka JavaScript.  
  
 Objekt JSON poskytuje dvě funkce pro převod na a z textového formátu JSON. [JSON.stringify](../javascript/reference/json-stringify-function-javascript.md) funkce serializuje objekty a pole do textu JSON. [JSON.Parse –](../javascript/reference/json-parse-function-javascript.md) funkce zrušte serializuje text JSON k vytvoření objektů v paměti. Další informace najdete v tématu [Úvod k JSON JavaScript Object Notation () v rozhraní .NET a používání jazyka JavaScript](http://go.microsoft.com/fwlink/?LinkId=124098).  
  
## <a name="see-also"></a>Viz také  
 [JavaScript – objekty](../javascript/reference/javascript-objects.md)