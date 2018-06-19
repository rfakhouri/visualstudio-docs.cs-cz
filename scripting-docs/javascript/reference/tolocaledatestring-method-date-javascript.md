---
title: toLocaleDateString – metoda (Date) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- toLocaleDateString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleDateString method
ms.assetid: 0b83715c-8ced-4bd7-8940-a8007d002d10
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6b4b019ad329a73bec13766932fbcadfa2ed133
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791895"
---
# <a name="tolocaledatestring-method-date-javascript"></a>toLocaleDateString – metoda (Date) (JavaScript)
Vrátí data jako hodnotu řetězce, který je vhodný pro aktuální národní prostředí hostitelské prostředí nebo zadaný národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.toLocaleDateString( [locales][, options])   
```  
  
#### <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. A `Date` objektu.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti porovnání.  
  
## <a name="remarks"></a>Poznámky  
 Od verze aplikace Internet Explorer 11, `toLocaleDateString` používá `Intl.DateTimeFormat` interně k formátování data, která přidává podporu pro `locales` a `options` parametry. Další informace o těchto parametrů najdete v tématu [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` a `options` parametry nejsou podporovány ve všech režimech dokumentů a verze prohlížeče. Další informace najdete v části požadavky.  
  
 Při použití `toLocaleDateString` v Internet Exploreru 10, režim starší režimech dokumentů a adaptivní režimu dokumentů standardy:  
  
-   Vrátí hodnotu řetězce, který obsahuje data v aktuálním časovém pásmu.  
  
-   Vrácený datum je ve výchozím nastavení formátu aktuální národní prostředí hostitelském prostředí.  
  
 V případě vynechání `locales` parametr návratovou hodnotu této metody nelze spoléhat ve vytváření skriptů, protože se bude lišit počítačů. V tomto scénáři použijte metodu pouze na formát zobrazený text – nikdy jako součást výpočet.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `toLocaleDateString` metoda s konkrétní možnosti porovnání a národní prostředí.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleDateString("en-US"));  
document.write(date.toLocaleDateString("ja-JP"));  
document.write(date.toLocaleDateString("ar-SA", options));  
document.write(date.toLocaleDateString("hi-IN", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013‎   
// ‎2013‎年‎2‎月‎1‎日‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales`a `options` parametry:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toDateString – metoda (Date)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString – metoda (Date)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)