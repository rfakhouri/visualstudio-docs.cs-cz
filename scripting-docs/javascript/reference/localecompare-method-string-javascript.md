---
title: "localeCompare – metoda (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: localeCompare
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: localeCompare method
ms.assetid: 66914079-12dd-4393-a84c-c05f58231c36
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 056a440d26c4ebf48bd762968fa32ea1efdfb443
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="localecompare-method-string-javascript"></a>localeCompare – metoda (String) (JavaScript)
Určuje, zda jsou dva řetězce ekvivalentní v aktuální národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringVar.localeCompare(stringExp[, locales][, options])   
```  
  
## <a name="parameters"></a>Parametry  
 `stringVar`  
 Požadováno. První řetězec určený k porovnání  
  
 `stringExp`  
 Požadováno. Druhý řetězec určený k porovnání  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript. Tento parametr musí odpovídat [BCP 47](http://tools.ietf.org/html/rfc5646) standardy; najdete [intl.collator – objekt](../../javascript/reference/intl-collator-object-javascript.md) podrobnosti.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti porovnání. najdete v článku [intl.collator – objekt](../../javascript/reference/intl-collator-object-javascript.md) podrobnosti.  
  
## <a name="remarks"></a>Poznámky  
 Pro porovnání řetězců, můžete určit buď `String` objekty nebo textové literály.  
  
 Od verze aplikace Internet Explorer 11, `localeCompare` používá `Intl.Collator` objektu interně k porovnání, které doplní o podporu `locales` a `options` parametry. Další informace o těchto parametrů najdete v tématu [Intl.Collator](../../javascript/reference/intl-collator-object-javascript.md) a [Intl.Collator.compare](../../javascript/reference/compare-property-intl-collator.md).  
  
> [!IMPORTANT]
>  `locales` a `options` parametry nejsou podporovány ve všech režimech dokumentů a verze prohlížeče. Další informace najdete v části požadavky.  
  
 `localeCompare` Metoda provádí porovnání řetězci zohledňující národního prostředí `stringVar` a `stringExp` a vrátí jednu z těchto výsledků, v závislosti na pořadí řazení výchozí národní prostředí systému:  
  
-   -1 v případě `stringVar` seřadí před `stringExp`.  
  
-   + Pokud 1 `stringVar` seřadí po `stringExp`.  
  
-   0 (nula), pokud jsou dva řetězce ekvivalentní.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak používat `localeCompare`.  
  
```JavaScript  
var str1 = "def";  
var str2 = "abc"  
  
document.write(str1.localeCompare(str2) + "<br/>");  
  
// Output: 1  
var str3 = "ghi";  
  
document.write(str1.localeCompare(str3)+ "<br/>");  
  
// Output: -1  
var str4 = "def";  
  
document.write(str1.localeCompare(str4));  
  
// Output: 0  
```  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak používat `localeCompare` v národním prostředí Němčina (Německo).  
  
```JavaScript  
var str1 = "a";  
var str2 = "b";  
  
document.write(str1.localeCompare(str2, "de-DE"));  
  
// Output  
// - 1  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `localeCompare` s německou národní prostředí a rozšíření specifická pro národní prostředí, které určuje pořadí řazení němčině telefonní seznamy. Tento příklad ukazuje rozdíly specifická pro národní prostředí.  
  
```JavaScript  
var arr = ["ä", "ad", "af", "a"];  
  
document.write(arr[0].localeCompare(arr[1], "de-DE-u-co-phonebk"));  // Returns 1  
document.write (arr[0].localeCompare(arr[2], "de-DE-u-co-phonebk"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE-u-co-phonebk"));  // Returns 1  
  
document.write (arr[0].localeCompare(arr[1], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[2], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE"));  // Returns 1  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales`a `options` parametry:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toLocaleString – metoda (Object)](../../javascript/reference/tolocalestring-method-object-javascript.md)