---
title: toLocaleString (datum) | Microsoft Docs
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
ms.assetid: 3472d7bd-b255-4804-8407-c4a1e419a5a3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6dc7b1f38f7e57d1c10f7197bb73b13b3545380
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tolocalestring-date"></a>toLocaleString (Date)
Převede data na řetězec pomocí zadané nebo aktuální národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.toLocaleString([locales][, options])   
```  
  
#### <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. `Date` Objekt, který chcete převést.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti porovnání.  
  
## <a name="remarks"></a>Poznámky  
 Od verze aplikace Internet Explorer 11, `toLocaleString` používá `Intl.DateTimeFormat` interně k porovnání Ujistěte se, které doplní o podporu `locales` a `options` parametry. Další informace o těchto parametrů najdete v tématu [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` a `options` parametry nejsou podporovány ve všech režimech dokumentů a verze prohlížeče. Další informace najdete v části požadavky.  
  
 Při použití `toLocaleString` v Internet Exploreru 10, režim starší režimech dokumentů a adaptivní režimu dokumentů standardy:  
  
-   Vrátí `String` objekt, který obsahuje data zapsána ve formátu dlouho výchozí aktuální národní prostředí.  
  
-   Pro kalendářní data mezi 1601 a roku. 1999 je datum formátovaného podle uživatele ovládacího panelu Místní nastavení.  
  
> [!NOTE]
>  V případě vynechání `locales` parametr, použijte `toLocaleString` pouze zobrazíte výsledky pro uživatele; nikdy nepoužívejte k výpočtu hodnot v rámci skriptu, protože na vrácený výsledek je specifický pro počítač.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `toLocaleString` metoda.  
  
```JavaScript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `toLocaleString` metoda s konkrétní možnosti porovnání a národní prostředí.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleString("en-US"));  
document.write(date.toLocaleString("ja-JP"));  
document.write(date.toLocaleString("ar-SA", options));  
document.write(date.toLocaleString("hi-IN", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013‎ ‎6‎:‎00‎:‎00‎ ‎AM  
// ‎2013‎年‎2‎月‎1‎日‎ ‎6‎:‎00‎:‎00  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales`a `options` parametry:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toLocaleDateString – metoda (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)