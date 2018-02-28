---
title: "@ifPříkaz (JavaScript) | Microsoft Docs"
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
- '@if_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- elif statement
- conditional statements, if
- if statement, @if
- else statement
- '@if statement'
ms.assetid: ff11b29d-c06a-4276-b11d-db73e2da98ac
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87cfc157ab16b183ccf687fa221393be4ab74757
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="if-statement-javascript"></a>@ifPříkaz (JavaScript)
Podmíněně spustí skupinu příkazů v závislosti na hodnotě výrazu.  
  
> [!WARNING]
>  Podmíněná kompilace se nepodporuje v režimu Standardy aplikace Internet Explorer 11 a [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Podmíněná kompilace je podporována v režimu standardů aplikace Internet Explorer 10 a ve všech dřívějších verzích.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      @if (  
   condition1  
)  
   text1  
[@elif (  
   condition2  
)  
   text2]  
[@else  
   text3]  
@end   
```  
  
## <a name="parameters"></a>Parametry  
 *Condition1 condition2*  
 Volitelné. Výraz, který lze převést na logický výraz.  
  
 `text1`  
 Volitelné. Text, který má být analyzován, pokud `condition1` je **true**.  
  
 `text2`  
 Volitelné. Text, který má být analyzován, pokud `condition1` je **false** a `condition2` je **true**.  
  
 `text3`  
 Volitelné. Text, který má být analyzovat, pokud obě `condition1` a `condition2` jsou **false**.  
  
## <a name="remarks"></a>Poznámky  
 Při psaní `@if` prohlášení, není nutné umístit každý klauzule na samostatném řádku. Můžete použít více  **@elif**  klauzule. Ale všechny  **@elif**  musí předcházet klauzule  **@else**  klauzule.  
  
 `@if` Příkaz se obvykle používá k určení, který text mezi několik možností, jak se mají použít pro výstup textu.  
  
 Použití proměnných podmíněné kompilace není běžné ve skriptech psaných pro stránky ASP nebo ASP.NET či programech příkazového řádku. Důvodem je skutečnost, že schopnosti kompilátoru lze určit pomocí jiných metod.  
  
 Při psaní skriptu pro webové stránky vždy vložte kód podmíněné kompilace do komentářů. To umožňuje hostitelům podmíněnou kompilaci ignorovat, pokud ji nepodporují.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití  **@if...@elif... @else... @end**  příkaz.  
  
```JavaScript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on a 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on a 16-bit version of Windows.");  
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
 [@cc_onPříkaz](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@setPříkaz](../../javascript/reference/at-set-statement-javascript.md)