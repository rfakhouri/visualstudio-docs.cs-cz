---
title: Informace o verzi JavaScript | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript, version information
ms.assetid: 440f4924-f7a9-48e0-873e-bd599a93b437
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a2335c3697be9ef3e2d674ac37047ddd3de242d
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="javascript-version-information"></a>JavaScript (informace o verzi)
Různé verze jazyka JavaScript podporují různé sady prvků JavaScript. [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace podporují mírně odlišné sadu funkcí, z Internet Exploreru.  
  
> [!IMPORTANT]
>  A [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace je nový typ aplikace, která běží na [!INCLUDE[win8](../../javascript/includes/win8-md.md)] zařízení. Chcete-li získat další informace o [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, najdete v části [co je aplikace pro Windows Store?](http://msdn.microsoft.com/en-us/231c1fba-9f87-468e-94aa-45dd57edcc70)  
  
 Režim, režim standardů (použito ve všech verzích Internet Explorer, až aplikace Internet Explorer 11, pokud je režim `<!doctype>` – direktiva) podporuje jinou sadu elementů než adaptivní režimu (režim používaná v žádné `<!doctype>` – direktiva). Další informace o správě verzí, naleznete v části [definování kompatibility dokumentu](http://go.microsoft.com/fwlink/?LinkId=208537).  
  
 Následující tabulky uvádí režimech dokumentů aplikace Internet Explorer (a aplikace pro Store představující [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] a [!INCLUDE[winphone_appname](../../javascript/reference/includes/winphone-appname-md.md)]) podporující konkrétní jazykové elementy. Režimech dokumentů, které podporují daného elementu se zobrazují písmenem **Y**, a jsou zobrazeny režimech dokumentů, které nepodporují daného elementu písmenem **N**.  
  
> [!IMPORTANT]
>  [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)] (Prohlížeč edge ve Windows 10) nezahrnuje podporu režimů starší verze dokumentu. Podpora pro [!INCLUDE[winphone_appname](../../javascript/reference/includes/winphone-appname-md.md)] aplikace spustí s Windows Phone 8.1. Povolenými experimentálními funkcemi (o: příznaky) jsou označeny "Exp."  
  
 Tabulka obsahuje souhrnné informace. Podrobnější informace najdete v dokumentaci pro element jazyka.  
  
|Prvek jazyka|Adaptivní režim, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7|Standardy aplikace Internet Explorer 8|Standardy aplikace Internet Explorer 9|Standardy aplikace Internet Explorer 10|Standardy aplikace Internet Explorer 11|Edge|Aplikace Windows Store|  
|----------------------|--------------------------------------------------------------------------|-----------------------------------|-----------------------------------|------------------------------------|------------------------------------|----------|----------------|  
|[__proto\_\_ Property (Object)](../../javascript/reference/proto-property-object-javascript.md)|N|N|N|N|A|A|v8: (Win): N<br />v8.1 (Win): Y<br />v8.1 (Phone): A|  
|[$1...$9 – vlastnosti (RegExp)](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[Vlastnost 0n](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md)|A|A|A|A|A|A|A|  
|[Funkce ABS](../../javascript/reference/math-abs-function-javascript.md)|A|A|A|A|A|A|A|  
|[ACOS – funkce](../../javascript/reference/math-acos-function-javascript.md)|A|A|A|A|A|A|A|  
|[acosh – funkce](../../javascript/reference/math-acosh-function-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[ActiveXObject – objekt](../../javascript/reference/activexobject-object-javascript.md)|A|A|A|A|A|A|N|  
|[Operátor sčítání a přiřazení (+=)](../../javascript/reference/addition-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor sčítání (+)](../../javascript/reference/addition-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Apply – metoda](../../javascript/reference/apply-method-function-javascript.md)|A|A|A|A|A|A|A|  
|[arguments – objekt](../../javascript/reference/arguments-object-javascript.md)|A|A|A|A|A|A|A|  
|[arguments – vlastnost](../../javascript/reference/arguments-property-function-javascript.md)|A|A|A|A|A|A|A|  
|[Array – objekt](../../javascript/reference/array-object-javascript.md)|A|A|A|A|A|A|A|  
|[Array.from – funkce (Array)](../../javascript/reference/array-from-function-array-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[Array.isArray – funkce](../../javascript/reference/array-isarray-function-javascript.md)|N|N|A|A|A|A|A|  
|[Array.of – funkce (Array)](../../javascript/reference/array-of-function-array-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[ArrayBuffer – objekt](../../javascript/reference/arraybuffer-object.md)|N|N|N|A|A|A|A|  
|[Funkce](../../javascript/functions-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[ASIN – funkce](../../javascript/reference/math-asin-function-javascript.md)|A|A|A|A|A|A|A|  
|[Object.assign – funkce (Object)](../../javascript/reference/object-assign-function-object-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[Operátor přiřazení (=)](../../javascript/reference/assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Atan – funkce](../../javascript/reference/math-atan-function-javascript.md)|A|A|A|A|A|A|A|  
|[ATAN2 – funkce](../../javascript/reference/math-atan2-function-javascript.md)|A|A|A|A|A|A|A|  
|[atEnd – metoda](../../javascript/reference/atend-method-enumerator-javascript.md)|A|A|A|A|A|A|N|  
|[BIND – metoda](../../javascript/reference/bind-method-function-javascript.md)|N|N|A|A|A|A|A|  
|[Bitový operátor AND a přiřazení (&=)](../../javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Bitový operátor AND (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Bitový operátor posunu vlevo (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Bitový operátor NOT (~)](../../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)|A|A|A|A|A|A|A|  
|[Bitový operátor přiřazení OR (&#124; =)](../../javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Bitový operátor OR – operátor (&#124;)](../../javascript/reference/bitwise-or-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Bitový operátor posunu vpravo (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor přiřazení bitové operace Astavit (^ =)](../../javascript/reference/bitwise-xor-assignment-operator-decrement-hat-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor bitového Astavit (^)](../../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)|A|A|A|A|A|A|A|  
|[BLINK – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[Bold – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[Boolean – objekt](../../javascript/reference/boolean-object-javascript.md)|A|A|A|A|A|A|A|  
|[break – příkaz](../../javascript/reference/break-statement-javascript.md)|A|A|A|A|A|A|A|  
|[volání metody](../../javascript/reference/call-method-function-javascript.md)|A|A|A|A|A|A|A|  
|[callee – vlastnost](../../javascript/reference/callee-property-arguments-javascript.md)|A|A|A|A|A|A|A|  
|[caller – vlastnost](../../javascript/reference/caller-property-function-javascript.md)|A|A|A|A|A|A|A|  
|[Catch – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)|A|A|A|A|A|A|A|  
|[ceil – funkce](../../javascript/reference/math-ceil-function-javascript.md)|A|A|A|A|A|A|A|  
|[charAt – metoda](../../javascript/reference/charat-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[charCodeAt – metoda](../../javascript/reference/charcodeat-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[class – příkaz](../../javascript/reference/class-statement-javascript.md)|N|N|N|N|N|Exp.|v8.1: N<br />v10: Exp.|  
|[codePointAt – metoda (String)](../../javascript/reference/codepointat-method-string-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Operátor čárka (,)](../../javascript/reference/comma-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[(Příkaz Komentář jeden řádek)](../../javascript/reference/comment-statements-javascript.md)|A|A|A|A|A|A|A|  
|[/*.. \*/ (Víceřádkových Comment příkaz)](../../javascript/reference/comment-statements-javascript.md)|A|A|A|A|A|A|A|  
|[Operátory porovnání](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Compile – metoda](../../javascript/reference/compile-method-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[concat – metoda (Array)](../../javascript/reference/concat-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[concat – metoda (String)](../../javascript/reference/concat-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)|A|A|A|A|N|N|N|  
|[Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)|A|A|A|A|N|N|N|  
|[Podmíněný (ternární) operátor (?:)](../../javascript/reference/conditional-ternary-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-object-javascript.md)|A|A|A|A|A|A|A|  
|[const – příkaz](../../javascript/reference/const-statement-javascript.md)|N|N|N|N|A|A|v8: (Win): N<br />v8.1 (Win): Y<br />v8.1 (Phone): A|  
|[continue – příkaz](../../javascript/reference/continue-statement-javascript.md)|A|A|A|A|A|A|A|  
|[Cos – funkce](../../javascript/reference/math-cos-function-javascript.md)|A|A|A|A|A|A|A|  
|[Create – funkce](../../javascript/reference/object-create-function-javascript.md)|N|N|A|A|A|A|A|  
|[DataView – objekt](../../javascript/reference/dataview-object.md)|N|N|N|A|A|A|A|  
|[Date – objekt](../../javascript/reference/date-object-javascript.md)|A|A|A|A|A|A|A|  
|[Debug – objekt](../../javascript/reference/debug-object-javascript.md)|A|A|A|A|A|A|A|  
|[Debug.setNonUserCodeExceptions – vlastnost](../../javascript/reference/debug-setnonusercodeexceptions-property.md)|N|N|N|A|A|A|A|  
|[Debug.setNonUserCodeExceptions – vlastnost](../../javascript/reference/debug-setnonusercodeexceptions-property.md)|N|N|N|A|A|A|A|  
|[debugger – příkaz](../../javascript/reference/debugger-statement-javascript.md)|A|A|A|A|A|A|A|  
|[decodeURI – funkce](../../javascript/reference/decodeuri-function-javascript.md)|A|A|A|A|A|A|A|  
|[Decodeuricomponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor snížení (--)](../../javascript/reference/increment-and-decrement-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Funkce](../../javascript/functions-javascript.md)|N|N|N|N|N|Exp.|v8.1: N<br />v10: Exp.|  
|[defineProperties – funkce](../../javascript/reference/object-defineproperties-function-javascript.md)|N|A*|A|A|A|A|A|  
|[defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md)|N|A*|A|A|A|A|A|  
|[delete – operátor](../../javascript/reference/delete-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[Description – vlastnost](../../javascript/reference/description-property-error-javascript.md)|A|A|A|A|A|A|A|  
|[Dimensions – metoda](../../javascript/reference/dimensions-method-vbarray-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor dělení a přiřazení (/=)](../../javascript/reference/division-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor dělení (/)](../../javascript/reference/division-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[do...while – příkaz](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)|A|A|A|A|A|A|A|  
|[E – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[encodeURI – funkce](../../javascript/reference/encodeuri-function-javascript.md)|A|A|A|A|A|A|A|  
|[Součást funkce encodeURI](../../javascript/reference/encodeuricomponent-function-javascript.md)|A|A|A|A|A|A|A|  
|[entries – metoda (Array)](../../javascript/reference/entries-method-array-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[Enumerator – objekt](../../javascript/reference/enumerator-object-javascript.md)|A|A|A|A|A|A|N|  
|[Number – konstanty](../../javascript/reference/number-constants-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[Operátor rovnosti (==)](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Error – objekt](../../javascript/reference/error-object-javascript.md)|A|A|A|A|A|A|A|  
|[stack – vlastnost (Error)](../../javascript/reference/stack-property-error-javascript.md)|N|N|N|A|A|A|A|  
|[stackTraceLimit – vlastnost (Error)](../../javascript/reference/stacktracelimit-property-error-javascript.md)|N|N|N|A|A|A|A|  
|[escape – funkce](../../javascript/reference/escape-function-javascript.md)|A|A|A|A|A|A|A|  
|[eval – funkce](../../javascript/reference/eval-function-javascript.md)|A|A|A|A|A|A|A|  
|[Exec – metoda](../../javascript/reference/exec-method-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[EVERY – metoda](../../javascript/reference/every-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[Exp – funkce](../../javascript/reference/math-exp-function-javascript.md)|A|A|A|A|A|A|A|  
|[fill – metoda (Array)](../../javascript/reference/fill-method-array-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[Filter – metoda](../../javascript/reference/filter-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[Finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)|A|A|A|A|A|A|A|  
|[findIndex – metoda (Array)](../../javascript/reference/findindex-method-array-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[fixed – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[Float32Array – objekt](../../javascript/reference/float32array-object.md)|N|N|N|A|A|A|A|  
|[Float64Array – objekt](../../javascript/reference/float64array-object.md)|N|N|N|A|A|A|A|  
|[Floor – funkce](../../javascript/reference/math-floor-function-javascript.md)|A|A|A|A|A|A|A|  
|[fontcolor – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[FontSize – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[for – příkaz](../../javascript/reference/for-statement-javascript.md)|A|A|A|A|A|A|A|  
|[foreach – metoda](../../javascript/reference/foreach-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[for...in – příkaz](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)|A|A|A|A|A|A|A|  
|[for...of – příkaz](../../javascript/reference/for-dot-dot-dot-of-statement-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)|N|N|A|A|A|A|A|  
|[fromCharCode – funkce](../../javascript/reference/string-fromcharcode-function-javascript.md)|A|A|A|A|A|A|A|  
|[fromCodePoint – funkce](../../javascript/reference/string-fromcodepoint-function-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Function – objekt](../../javascript/reference/function-object-javascript.md)|A|A|A|A|A|A|A|  
|[function – příkaz](../../javascript/reference/function-statement-javascript.md)|A|A|A|A|A|A|A|  
|[Generátory](../../javascript/advanced/iterators-and-generators-javascript.md)|N|N|N|N|N|Exp.|v8.1: N<br />v10: Exp.|  
|[getDate – metoda](../../javascript/reference/getdate-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getDay – metoda](../../javascript/reference/getday-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getFullYear – metoda](../../javascript/reference/getfullyear-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getHours – metoda](../../javascript/reference/gethours-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getItem – metoda](../../javascript/reference/getitem-method-vbarray-javascript.md)|A|A|A|A|A|A|A|  
|[getMilliseconds – metoda](../../javascript/reference/getmilliseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getMinutes – metoda](../../javascript/reference/getminutes-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getMonth – metoda](../../javascript/reference/getmonth-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[GetObject – funkce](../../javascript/reference/getobject-function-javascript.md)|A|A|N|N|N|N|N|  
|[getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)|N|A*|A|A|A|A|A|  
|[getOwnPropertyNames Function](../../javascript/reference/object-getownpropertynames-function-javascript.md)|N|N|A|A|A|A|A|  
|[getprototypeof – funkce](../../javascript/reference/object-getprototypeof-function-javascript.md)|N|N|A|A|A|A|A|  
|[getSeconds – metoda](../../javascript/reference/getseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getTime – metoda](../../javascript/reference/gettime-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getTimezoneOffset – metoda](../../javascript/reference/gettimezoneoffset-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCDate – metoda](../../javascript/reference/getutcdate-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCDay – metoda](../../javascript/reference/getutcday-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCFullYear – metoda](../../javascript/reference/getutcfullyear-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCHours – metoda](../../javascript/reference/getutchours-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCMilliseconds – metoda](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCMinutes – metoda](../../javascript/reference/getutcminutes-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCMonth – metoda](../../javascript/reference/getutcmonth-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getUTCSeconds – metoda](../../javascript/reference/getutcseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[getVarDate – metoda](../../javascript/reference/getvardate-method-date-javascript.md)|A|A|A|A|A|A|N|  
|[getYear – metoda](../../javascript/reference/getyear-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[Global – objekt](../../javascript/reference/global-object-javascript.md)|A|A|A|A|A|A|A|  
|[Global – vlastnost](../../javascript/reference/global-property-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[Větší než (>) – operátor](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Větší než nebo rovno – operátor (> =)](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[hasOwnProperty – metoda](../../javascript/reference/hasownproperty-method-object-javascript.md)|A|A|A|A|A|A|A|  
|[Metody značek HTML](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[hypot – funkce](../../javascript/reference/math-hypot-function-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Operátor identity (=)](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[if...else – příkaz](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)|A|A|A|A|A|A|A|  
|[IgnoreCase – vlastnost](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[imul – funkce](../../javascript/reference/math-imul-function-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[In – operátor](../../javascript/reference/in-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[includes – metoda (String)](../../javascript/reference/includes-method-string-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Operátor přírůstku (++)](../../javascript/reference/increment-and-decrement-operators-javascript.md)|A|A|A|A|A|A|A|  
|[index – vlastnost](../../javascript/reference/index-property-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[indexOf – metoda (Array)](../../javascript/reference/indexof-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[indexOf – metoda (String)](../../javascript/reference/indexof-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor nerovnosti (! =)](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Infinity – konstanta](../../javascript/reference/infinity-constant-javascript.md)|A|A|A|A|A|A|A|  
|[Input – vlastnost ($_)](../../javascript/reference/input-property-dollar-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[instanceof – operátor](../../javascript/reference/instanceof-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[Int8Array – objekt](../../javascript/reference/int8array-object.md)|N|N|N|A|A|A|A|  
|[Int16Array – objekt](../../javascript/reference/int16array-object.md)|N|N|N|A|A|A|A|  
|[Int32Array – objekt](../../javascript/reference/int32array-object.md)|N|N|N|A|A|A|A|  
|[Intl.Collator – objekt](../../javascript/reference/intl-collator-object-javascript.md)|N|N|N|N|A|A|v8: (Win): N<br />v8.1 (Win): Y<br />v8.1 (Phone): A|  
|[Intl.DateTimeFormat – objekt](../../javascript/reference/intl-datetimeformat-object-javascript.md)|N|N|N|N|A|A|v8: N<br />v8.1: A|  
|[Intl.NumberFormat – objekt](../../javascript/reference/intl-numberformat-object-javascript.md)|N|N|N|N|A|A|v8: N<br />v8.1: A|  
|[isFinite – funkce](../../javascript/reference/isfinite-function-javascript.md)|A|A|A|A|A|A|A|  
|[IsArray – funkce](../../javascript/reference/array-isarray-function-javascript.md)|N|N|A|A|A|A|A|  
|[Isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)|N|N|A|A|A|A|A|  
|[isFrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)|N|N|A|A|A|A|A|  
|[isInteger – funkce](../../javascript/reference/number-isinteger-function-number-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[isNaN – funkce](../../javascript/reference/isnan-function-javascript.md)|A|A|A|A|A|A|A|  
|[isNaN – funkce (Number)](../../javascript/reference/number-isnan-function-number-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Data formátu ISO](../../javascript/date-and-time-strings-javascript.md)|N|N|A|A|A|A|A|  
|[IsPrototypeOf – metoda](../../javascript/reference/isprototypeof-method-object-javascript.md)|A|A|A|A|A|A|A|  
|[issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)|N|N|A|A|A|A|A|  
|[italics – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[Iterátory](../../javascript/advanced/iterators-and-generators-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Item – metoda](../../javascript/reference/item-method-enumerator-javascript.md)|A|A|A|A|A|A|A|  
|[JOIN – metoda](../../javascript/reference/join-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[JSON – objekt](../../javascript/reference/json-object-javascript.md)|N|A|A|A|A|A|A|  
|[Keys – funkce](../../javascript/reference/object-keys-function-javascript.md)|N|N|A|A|A|A|A|  
|[keys – metoda (Array)](../../javascript/reference/keys-method-array-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Příkaz s návěstím](../../javascript/reference/labeled-statement-javascript.md)|A|A|A|A|A|A|A|  
|[lastIndex – vlastnost](../../javascript/reference/lastindex-property-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[lastIndexOf – metoda (Array)](../../javascript/reference/lastindexof-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[lastIndexOf – metoda (String)](../../javascript/reference/lastindexof-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[lastMatch Property ($&)](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[lastparen – vlastnost ($ +)](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[LBound – metoda](../../javascript/reference/lbound-method-vbarray-javascript.md)|A|A|A|A|A|A|A|  
|[leftcontext – vlastnost ($')](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor posunu vlevo a přiřazení (<<=)](../../javascript/reference/left-shift-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Length – vlastnost (Arguments)](../../javascript/reference/length-property-arguments-javascript.md)|A|A|A|A|A|A|A|  
|[length – vlastnost (Array)](../../javascript/reference/length-property-array-javascript.md)|A|A|A|A|A|A|A|  
|[length – vlastnost (Function)](../../javascript/reference/length-property-function-javascript.md)|A|A|A|A|A|A|A|  
|[length – vlastnost (String)](../../javascript/reference/length-property-string-javascript.md)|A|A|A|A|A|A|A|  
|[Menší než (<) – operátor](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Menší než nebo rovno – operátor (< =)](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[let – příkaz](../../javascript/reference/let-statement-javascript.md)|N|N|N|N|A|A|v8: N<br />v8.1: A|  
|[odkaz – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[LN2 – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[LN10 – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[localeCompare – metoda](../../javascript/reference/localecompare-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[log – funkce](../../javascript/reference/math-log-function-javascript.md)|A|A|A|A|A|A|A|  
|[Log2e – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Log10e – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Logický operátor AND (&&)](../../javascript/reference/logical-and-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Logický operátor NOT (!)](../../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)|A|A|A|A|A|A|A|  
|[Logické OR – operátor (&#124; &#124;)](../../javascript/reference/logical-or-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[map – metoda](../../javascript/reference/map-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[Map – objekt](../../javascript/reference/map-object-javascript.md)|N|N|N|N|A|A|v8: N<br />v8.1: A|  
|[Match – metoda](../../javascript/reference/match-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Math – objekt](../../javascript/reference/math-object-javascript.md)|A|A|A|A|A|A|A|  
|[Max – funkce](../../javascript/reference/math-max-function-javascript.md)|A|A|A|A|A|A|A|  
|[MAX_VALUE – konstanta](../../javascript/reference/number-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Message – vlastnost](../../javascript/reference/message-property-error-javascript.md)|A|A|A|A|A|A|A|  
|[min – funkce](../../javascript/reference/math-min-function-javascript.md)|A|A|A|A|A|A|A|  
|[MIN_VALUE – konstanta](../../javascript/reference/number-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Remainder – operátor přiřazení (% =)](../../javascript/reference/modulus-assignment-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor zbytku (%)](../../javascript/reference/modulus-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[moveFirst – metoda](../../javascript/reference/movefirst-method-enumerator-javascript.md)|A|A|A|A|A|A|A|  
|[moveNext – metoda](../../javascript/reference/movenext-method-enumerator-javascript.md)|A|A|A|A|A|A|A|  
|[Multiline – vlastnost](../../javascript/reference/multiline-property-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor násobení a přiřazení (*=)](../../javascript/reference/multiplication-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor násobení (*)](../../javascript/reference/multiplication-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[Name – vlastnost](../../javascript/reference/name-property-error-javascript.md)|A|A|A|A|A|A|A|  
|[NaN – konstanta (globální)](../../javascript/reference/nan-constant-javascript.md)|A|A|A|A|A|A|A|  
|[NaN – konstanta (Number)](../../javascript/reference/number-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Negative_infinity – konstanta](../../javascript/reference/number-constants-javascript.md)|A|A|A|A|A|A|A|  
|[new – operátor](../../javascript/reference/new-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[Nonidentity – operátor (! ==)](../../javascript/reference/comparison-operators-javascript.md)|A|A|A|A|A|A|A|  
|[Funkce Now](../../javascript/reference/date-now-function-javascript.md)|N|N|A|A|A|A|A|  
|[Number – objekt](../../javascript/reference/number-object-javascript.md)|A|A|A|A|A|A|A|  
|[Vlastnost počtu](../../javascript/reference/number-property-error-javascript.md)|A|A|A|A|A|A|A|  
|[Object – objekt](../../javascript/reference/object-object-javascript.md)|A|A|A|A|A|A|A|  
|[Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)|A|A|A|A|A|A|A|  
|[Date.parse – funkce](../../javascript/reference/date-parse-function-javascript.md)|A|A|A|A|A|A|A|  
|[JSON.parse – funkce](../../javascript/reference/json-parse-function-javascript.md)|N|A|A|A|A|A|A|  
|[parseFloat – funkce](../../javascript/reference/parsefloat-function-javascript.md)|A|A|A|A|A|A|A|  
|[parseInt – funkce](../../javascript/reference/parseint-function-javascript.md)|A|A|A|A|A|A|A|  
|[PI – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[POP – metoda](../../javascript/reference/pop-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[Positive_infinity – konstanta](../../javascript/reference/number-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Funkce POW](../../javascript/reference/math-pow-function-javascript.md)|A|A|A|A|A|A|A|  
|[preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md)|N|N|A|A|A|A|A|  
|[Promise – objekt](../../javascript/reference/promise-object-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-object-javascript.md)|A|A|A|A|A|A|A|  
|[propertyIsEnumerable – metoda](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|A|A|A|A|A|A|A|  
|[Proxy – objekt](../../javascript/reference/proxy-object-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[push – metoda](../../javascript/reference/push-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[náhodné – funkce](../../javascript/reference/math-random-function-javascript.md)|A|A|A|A|A|A|A|  
|[Nezpracovaná – funkce](../../javascript/reference/string-raw-function-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[reduce – metoda](../../javascript/reference/reduce-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[reduceright – metoda](../../javascript/reference/reduceright-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)|A|A|A|A|A|A|A|  
|[Regulární výraz – objekt](../../javascript/reference/regular-expression-object-javascript.md)|A|A|A|A|A|A|A|  
|[Syntax regulárních výrazů](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)|A|A|A|A|A|A|A|  
|[Příznak /y regulární výraz](../../javascript/reference/regular-expression-object-javascript.md)|N|N|N|N|N|Exp.|v8.1: N<br />v10: Exp.|  
|[repeat – metoda (String)](../../javascript/reference/repeat-method-string-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[replace – metoda](../../javascript/reference/replace-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Funkce](../../javascript/functions-javascript.md)|N|N|N|N|N|N|v8.1: N<br />v10: Y|  
|[return – příkaz](../../javascript/reference/return-statement-javascript.md)|A|A|A|A|A|A|A|  
|[reverse – metoda](../../javascript/reference/reverse-method-javascript.md)|A|A|A|A|A|A|A|  
|[rightcontext – vlastnost ($')](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor posunu vpravo a přiřazení (>>=)](../../javascript/reference/right-shift-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Round – funkce](../../javascript/reference/math-round-function-javascript.md)|A|A|A|A|A|A|A|  
|[ScriptEngine – funkce](../../javascript/reference/scriptengine-function-javascript.md)|A|A|A|A|A|A|A|  
|[ScriptEngineBuildVersion – funkce](../../javascript/reference/scriptenginebuildversion-function-javascript.md)|A|A|A|A|A|A|A|  
|[ScriptEngineMajorVersion – funkce](../../javascript/reference/scriptenginemajorversion-function-javascript.md)|A|A|A|A|A|A|A|  
|[ScriptEngineMinorVersion – funkce](../../javascript/reference/scriptengineminorversion-function-javascript.md)|A|A|A|A|A|A|A|  
|[Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)|N|N|A|A|A|A|A|  
|[Search – metoda](../../javascript/reference/search-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Set – objekt](../../javascript/reference/set-object-javascript.md)|N|N|N|N|A|A|v8: N<br />v8.1: A|  
|[setDate – metoda](../../javascript/reference/setdate-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setFullYear – metoda](../../javascript/reference/setfullyear-method-date-javascript.md)||A|A|A|A|A|A|  
|[setHours – metoda](../../javascript/reference/sethours-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setmilliseconds – metoda](../../javascript/reference/setmilliseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setMinutes – metoda](../../javascript/reference/setminutes-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setMonth – metoda](../../javascript/reference/setmonth-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setSeconds – metoda](../../javascript/reference/setseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setTime – metoda](../../javascript/reference/settime-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCDate – metoda](../../javascript/reference/setutcdate-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCFullYear – metoda](../../javascript/reference/setutcfullyear-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCHours – metoda](../../javascript/reference/setutchours-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCMilliseconds – metoda](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCMinutes – metoda](../../javascript/reference/setutcminutes-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCMonth – metoda](../../javascript/reference/setutcmonth-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setUTCSeconds – metoda](../../javascript/reference/setutcseconds-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[setYear – metoda](../../javascript/reference/setyear-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[SHIFT – metoda](../../javascript/reference/shift-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[Sin – Funkce](../../javascript/reference/math-sin-function-javascript.md)|A|A|A|A|A|A|A|  
|[slice – metoda (Array)](../../javascript/reference/slice-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[slice – metoda (String)](../../javascript/reference/slice-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Small – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[SOME – metoda](../../javascript/reference/some-method-array-javascript.md)|N|N|A|A|A|A|A|  
|[sort – metoda](../../javascript/reference/sort-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[Source – vlastnost](../../javascript/reference/source-property-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[splice – metoda](../../javascript/reference/splice-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[split – metoda](../../javascript/reference/split-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Funkce](../../javascript/functions-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Sqrt – funkce](../../javascript/reference/math-sqrt-function-javascript.md)|A|A|A|A|A|A|A|  
|[Sqrt1_2 – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[Sqrt2 – konstanta](../../javascript/reference/math-constants-javascript.md)|A|A|A|A|A|A|A|  
|[use strict – direktiva](../../javascript/reference/use-strict-directive.md)|N|N|N|A|A|A|A|  
|[Vytvořit – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[String – objekt](../../javascript/reference/string-object-javascript.md)|A|A|A|A|A|A|A|  
|[JSON.stringify – funkce](../../javascript/reference/json-stringify-function-javascript.md)|N|A|A|A|A|A|A|  
|[Sub – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[substr – metoda](../../javascript/reference/substr-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[substring – metoda](../../javascript/reference/substring-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor odčítání a přiřazení (-=)](../../javascript/reference/subtraction-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor odčítání (-)](../../javascript/reference/subtraction-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[sup – metoda](../../javascript/reference/html-tag-methods-javascript.md)|A|A|A|A|A|A|A|  
|[switch – příkaz](../../javascript/reference/switch-statement-javascript.md)|A|A|A|A|A|A|A|  
|[Symbol – objekt](../../javascript/reference/symbol-object-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Tan – Funkce](../../javascript/reference/math-tan-function-javascript.md)|A|A|A|A|A|A|A|  
|[Řetězce šablon](../../javascript/advanced/template-strings-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[Test – metoda](../../javascript/reference/test-method-regular-expression-javascript.md)|A|A|A|A|A|A|A|  
|[this – příkaz](../../javascript/reference/this-statement-javascript.md)|A|A|A|A|A|A|A|  
|[throw – příkaz](../../javascript/reference/throw-statement-javascript.md)|A|A|A|A|A|A|A|  
|[toArray – metoda](../../javascript/reference/toarray-method-vbarray-javascript.md)|A|A|A|A|A|A|A|  
|[toDateString – metoda](../../javascript/reference/todatestring-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[toExponential – metoda](../../javascript/reference/toexponential-method-number-javascript.md)|A|A|A|A|A|A|A|  
|[toFixed – metoda](../../javascript/reference/tofixed-method-number-javascript.md)|A|A|A|A|A|A|A|  
|[toGMTString – metoda](../../javascript/reference/togmtstring-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[toisostring – metoda](../../javascript/reference/toisostring-method-date-javascript.md)|N|N|A|A|A|A|A|  
|[tojson – metoda](../../javascript/reference/tojson-method-date-javascript.md)|N|A|A|A|A|A|A|  
|[toLocaleDateString – metoda](../../javascript/reference/tolocaledatestring-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[toLocaleLowercase – metoda](../../javascript/reference/tolocalelowercase-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[toLocaleString – metoda](../../javascript/reference/tolocalestring-method-object-javascript.md)|A|A|A|A|A|A|A|  
|[toLocaleTimeString – metoda](../../javascript/reference/tolocaletimestring-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[tolocaleuppercase – metoda](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[toLowerCase – metoda](../../javascript/reference/tolowercase-method-javascript.md)|A|A|A|A|A|A|A|  
|[toPrecision – metoda](../../javascript/reference/toprecision-method-number-javascript.md)|A|A|A|A|A|A|A|  
|[toString – metoda](../../javascript/reference/tostring-method-object-javascript.md)|A|A|A|A|A|A|A|  
|[toTimeString – metoda](../../javascript/reference/totimestring-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[toUpperCase – metoda](../../javascript/reference/touppercase-method-string-javascript.md)|A|A|A|A|A|A|A|  
|[toUTCString – metoda](../../javascript/reference/toutcstring-method-date-javascript.md)|A|A|A|A|A|A|A|  
|[Trim – metoda](../../javascript/reference/trim-method-string-javascript.md)|N|N|A|A|A|A|A|  
|[Try – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)|A|A|A|A|A|A|A|  
|[typeof – operátor](../../javascript/reference/typeof-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[UBound – metoda](../../javascript/reference/ubound-method-vbarray-javascript.md)|A|A|A|A|A|A|A|  
|[Uint8Array – objekt](../../javascript/reference/uint8array-object.md)|N|N|N|A|A|A|A|  
|[Uint16Array – objekt](../../javascript/reference/uint16array-object.md)|N|N|N|A|A|A|A|  
|[Uint32Array – objekt](../../javascript/reference/uint32array-object.md)|N|N|N|A|A|A|A|  
|[Uint8ClampedArray – objekt](../../javascript/reference/uint8clampedarray-object-javascript.md)|N|N|N|N|A|A|v8:: Ne<br />v8.1 (Win): Ano<br />v8.1 (Phone): Ne<br />v10: Y|  
|[Operátor unární negace (-)](../../javascript/reference/subtraction-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[undefined – konstanta](../../javascript/reference/undefined-constant-javascript.md)|A|A|A|A|A|A|A|  
|[unescape – funkce](../../javascript/reference/unescape-function-javascript.md)|A|A|A|A|A|A|A|  
|[Unicode kód bodu řídicí znaky](../../javascript/advanced/special-characters-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[unshift – metoda](../../javascript/reference/unshift-method-array-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor posunu vpravo bez znaménka a přiřazení (>>>=)](../../javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript.md)|A|A|A|A|A|A|A|  
|[Operátor posunu vpravo bez znaménka (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)|A|A|A|A|A|A|A|  
|[use strict – direktiva](../../javascript/reference/use-strict-directive.md)|N|N|N|A|A|A|A|  
|[UTC – funkce](../../javascript/reference/date-utc-function-javascript.md)|A|A|A|A|A|A|A|  
|[valueOf – metoda](../../javascript/reference/valueof-method-object-javascript.md)|A|A|A|A|A|A|A|  
|[values – metoda (Array)](../../javascript/reference/values-method-array-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[var – příkaz](../../javascript/reference/var-statement-javascript.md)|A|A|A|A|A|A|A|  
|[VBArray – objekt](../../javascript/reference/vbarray-object-javascript.md)|A|A|A|A|A|A|N|  
|[void – operátor](../../javascript/reference/void-operator-decrementjavascript.md)|A|A|A|A|A|A|A|  
|[WeakMap – objekt](../../javascript/reference/weakmap-object-javascript.md)|N|N|N|N|A|A|v8: N<br />v8.1: A|  
|[WeakSet – objekt](../../javascript/reference/weakset-object-javascript.md)|N|N|N|N|N|A|v8.1: N<br />v10: Y|  
|[while – příkaz](../../javascript/reference/while-statement-javascript.md)|A|A|A|A|A|A|A|  
|[WinRTError – objekt](../../javascript/reference/winrterror-object-javascript.md)|N|N|N|A|A|A|A|  
|[with – příkaz](../../javascript/reference/with-statement-javascript.md)|A|A|A|A|A|A|A|  
|[Write – funkce](../../javascript/reference/debug-write-function-javascript.md)|A|A|A|A|A|A|A|  
|[writeln – funkce](../../javascript/reference/debug-writeln-function-javascript.md)|A|A|A|A|A|A|A|  
  
 \* Podporuje objekty DOM však není uživatelem definované objekty. `enumerable` a `configurable` atributy lze zadat, ale nebudou použity.  
  
## <a name="see-also"></a>Viz také  
 [Definování kompatibility dokumentu](http://go.microsoft.com/fwlink/?LinkId=208537)