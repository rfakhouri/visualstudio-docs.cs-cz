---
title: "Proměnné (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- coercion
- case sensitivity, JavaScript variable name
ms.assetid: 12a450e5-4818-4a09-9878-cd7c6cd2a248
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f30946899ad35286dfb1e786cf903d58f5c98cb6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="variables-javascript"></a>Proměnné (JavaScript)
V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], proměnná obsahuje hodnotu, jako je například "hello" nebo 5. Pokud použijete proměnnou, odkazujete na data je představuje, například `NumberOfDaysLeft = EndDate - TodaysDate`.  
  
 Proměnné se používají k ukládání, načítat a pracovat s hodnotami, které se zobrazují v kódu. Pokuste se zadejte smysluplný název snadno ostatním uživatelům pochopit, co kód dělá proměnných.  
  
## <a name="declaring-variables"></a>Deklarování proměnných  
 Při prvním proměnné se zobrazí ve vašem skriptu je jeho deklaraci. První zmínky proměnné nastaví ho v paměti, takže je možné odkazovat na ni později na váš skript. Před použitím je by měly deklarovat proměnné. To provedete pomocí `var` – klíčové slovo.  
  
```JavaScript  
// A single declaration.  
var count;    
// Multiple declarations with a single var keyword.  
var count, amount, level;      
// Variable declaration and initialization in one statement.  
var count = 0, amount = 100;   
```  
  
 Pokud není inicializovat vaše proměnná v `var` příkaz automaticky trvá na hodnotě `undefined`.  
  
## <a name="naming-variables"></a>Názvy proměnných  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]je malá a velká písmena jazyk. To znamená, že název proměnné, jako **Můjčítač** se liší od názvu proměnné **Můjčítač**. Názvy proměnných může být o libovolné délce. Pravidla pro vytváření právní názvy proměnných jsou následující:  
  
-   První znak musí být k písmenu ASCII (velká nebo malá písmena) nebo znakem podtržítka (_). Všimněte si, že číslo nelze použít jako první znak.  
  
-   Následující znaky musí být písmena, čísla nebo podtržítka (_).  
  
-   Název proměnné nesmí být [vyhrazené slovo](../javascript/reference/javascript-reserved-words.md).  
  
 Tady jsou některé příklady platné názvy proměnných:  
  
```  
_pagecount   
Part9   
Number_Items   
```  
  
 Tady jsou některé příklady neplatných názvů proměnných:  
  
```JavaScript  
// Cannot begin with a number.   
99Balloons     
// The ampersand (&) character is not a valid character for variable names.   
Alpha&Beta   
```  
  
 Pokud chcete deklarovat proměnnou a provést jeho inicializaci, ale nechcete, aby u ní žádné konkrétní hodnotu, přiřaďte mu hodnotu `null`. Zde je příklad.  
  
```JavaScript  
var bestAge = null;  
var muchTooOld = 3 * bestAge; // muchTooOld has the value 0.  
```  
  
 Pokud je deklarovat proměnnou bez přiřazení hodnoty, má hodnotu `undefined`. Zde je příklad.  
  
```JavaScript  
var currentCount;  
// finalCount has the value NaN because currentCount is undefined.  
var finalCount = 1 * currentCount;   
```  
  
 `null` Hodnota se chová jako číslo 0, zatímco `undefined` chová jako speciální hodnota `NaN` (není číslo). Při porovnání `null` hodnotu a `undefined` hodnotu, jsou stejné.  
  
 Je možné deklarovat proměnnou bez použití `var` – klíčové slovo v deklaraci a přiřadit hodnotu k ní. Toto je implicitní deklarace.  
  
```JavaScript  
// The variable noStringAtAll is declared implicitly.  
noStringAtAll = "";   
```  
  
 Nemůžete použít proměnné, která se nikdy bylo deklarováno.  
  
```JavaScript  
// Error. Length and width do not yet exist.  
var area = length * width;   
```  
  
## <a name="coercion"></a>Převod  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]je volného typu jazyk, oproti silného typu jazyky jako C++. To znamená, že proměnné JavaScript mají žádný předem určený typ. Typ proměnné místo toho je typ jeho hodnoty. Toto chování umožňuje považovat hodnotu, jako by šlo jiného typu.  
  
 V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], aniž by došlo k výjimce můžete provádět operace na hodnoty různých typů. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] Překladač implicitně převede, nebo *převede*, jeden dat typy do druhé a pak provede operaci. Pravidla pro převod řetězce, počet a logické hodnoty jsou následující:  
  
-   Pokud přidáte řetězec a číslo, číslo sloučen s řetězec.  
  
-   Pokud přidáte řetězec a logickou hodnotu, se má logickou hodnotu na řetězec.  
  
-   Pokud přidáte číslo a logickou hodnotu, logická hodnota sloučen s číslem.  
  
 V následujícím příkladu číslo přidat do výsledků řetězec v řetězci.  
  
```JavaScript  
var x = 2000;  
var y = "Hello";  
// The number is coerced to a string.  
x = x + y;  
document.write(x);   
  
// Output:  
// 2000Hello  
```  
  
 Řetězce jsou automaticky převedeny na ekvivalentní čísla pro účely porovnání. Chcete-li explicitně převést řetězec na celé číslo, použijte [funkce parseInt](../javascript/reference/parseint-function-javascript.md). Chcete-li explicitně převést řetězec na číslo, použijte [funkce parseFloat](../javascript/reference/parsefloat-function-javascript.md).