---
title: "@cc_onPříkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '@cc_on_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, activating
- '@cc_on statement'
- '@set statement'
- '@if statement'
ms.assetid: fdeda7ee-b9f4-4e52-8aa2-21c90c02a332
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e993d5bc8302931a5722495da70612e79f7dfd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="ccon-statement-javascript"></a>@cc_onPříkaz (JavaScript)
Aktivuje podporu podmíněné kompilace uvnitř komentářů ve skriptu.  
  
> [!WARNING]
>  Podmíněná kompilace se nepodporuje v režimu Standardy aplikace Internet Explorer 11 a [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Podmíněná kompilace je podporována v režimu standardů aplikace Internet Explorer 10 a ve všech dřívějších verzích.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
@cc_on   
```  
  
## <a name="remarks"></a>Poznámky  
 `@cc_on` Příkaz aktivuje Podmíněná kompilace v rámci komentáře ve skriptu.  
  
 Použití proměnných podmíněné kompilace není běžné ve skriptech psaných pro stránky ASP nebo ASP.NET či v programech příkazového řádku, protože schopnosti kompilátoru lze zjistit pomocí jiných metod.  
  
 Při psaní skriptu pro webové stránky vždy umístěte kód podmíněné kompilace do komentářů. To umožňuje hostitelům podmíněnou kompilaci ignorovat, pokud ji nepodporují.  
  
 Důrazně doporučujeme použít `@cc_on` příkaz v komentář, tak, aby prohlížeče, které nepodporují Podmíněná kompilace přijme váš skript jako platné syntaxe:  
  
 `@if` Nebo `@set` příkaz mimo komentář také aktivuje Podmíněná kompilace.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `@cc_on` příkaz.  
  
```JavaScript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on the 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on the 16-bit version of Windows.");  
    @else  
        document.write("Running on a different operating system.");  
    @end  
@*/  
```  
  
## <a name="requirements"></a>Požadavky  
 V všechny verze aplikace Internet Explorer, ale není v podporované [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@ifPříkaz](../../javascript/reference/at-if-statement-javascript.md)   
 [@setPříkaz](../../javascript/reference/at-set-statement-javascript.md)