---
title: "toLocaleTimeString – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- toLocaleTimeString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleTimeString method
ms.assetid: 8ad75bf5-864c-4a2a-be90-220e87dce172
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77d8ee8fb6757b13da22a3cf3a59d28a105292cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tolocaletimestring-method-date-javascript"></a>toLocaleTimeString – metoda (Date) (JavaScript)
Vrátí dobu jako hodnotu řetězce, který je vhodný pro aktuální národní prostředí hostitelské prostředí nebo zadaný národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.toLocaleTimeString([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. A `Date` objektu.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti porovnání.  
  
## <a name="remarks"></a>Poznámky  
 Od verze aplikace Internet Explorer 11, `toLocaleTimeString` používá `Intl.DateTimeFormat` interně k formátování času, který přidává podporu pro `locales` a `options` parametry. Další informace o těchto parametrů najdete v tématu [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` a `options` parametry nejsou podporovány ve všech režimech dokumentů a verze prohlížeče. Další informace najdete v části požadavky.  
  
 Při použití `toLocaleTimeString` v Internet Exploreru 10, režim starší režimech dokumentů a adaptivní režimu dokumentů standardy:  
  
-   Vrátí hodnotu řetězce, který obsahuje čas v aktuální časové pásmo.  
  
-   Vrácený čas je ve výchozím nastavení formátu aktuální národní prostředí hostitelském prostředí.  
  
 V případě vynechání `locales` parametr návratovou hodnotu této metody nelze spoléhat ve vytváření skriptů, protože se bude lišit počítačů. V tomto scénáři použijte metodu pouze na formát zobrazený text – nikdy jako součást výpočet.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `toLocaleTimeString` metoda s konkrétní možnosti porovnání a národní prostředí.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleTimeString("en-US"));  
document.write(date.toLocaleTimeString("ja-JP"));  
document.write(date.toLocaleTimeString("ar-SA", options));  
document.write(date.toLocaleTimeString("hi-IN", options));  
  
// Output:  
// ‎‎6‎:‎00‎:‎00‎ ‎AM ‎   
// 6‎:‎00‎:‎00‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤ ٠٦‎:‎٠٠‎:‎٠٠‎ ‎ص  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013 06:00:00  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales`a `options` parametry:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toTimeString – metoda (Date)](../../javascript/reference/totimestring-method-date-javascript.md)   
 [toLocaleDateString – metoda (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)