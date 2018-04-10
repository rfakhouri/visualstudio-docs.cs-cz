---
title: '@set Příkaz (JavaScript) | Microsoft Docs'
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
- '@set_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '@set statement'
- conditional compilation, variables
ms.assetid: 36f15926-3e69-422d-82a2-d186dc088203
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10f74a1d57a61d78897b660812a6fd8078244b6b
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="set-statement-javascript"></a>@set Statement (JavaScript)
Vytvoří proměnné používané s příkazy podmíněné kompilace.  
  
> [!WARNING]
>  Podmíněná kompilace se nepodporuje v režimu Standardy aplikace Internet Explorer 11 a [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Podmíněná kompilace je podporována v režimu standardů aplikace Internet Explorer 10 a ve všech dřívějších verzích.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
@set @varname = term   
```  
  
## <a name="parameters"></a>Parametry  
 *název_proměnné*  
 Požadováno. Platný [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] název proměnné. Vždy musí začínat znakem „@“.  
  
 `term`  
 Požadováno. Nula nebo více unárních operátorů následovaných konstantou, proměnnou podmíněné kompilace nebo výrazem v závorkách.  
  
## <a name="remarks"></a>Poznámky  
 V podmíněné kompilaci jsou podporovány číselné proměnné a proměnné typu Boolean. Řetězce podporovány nejsou. Proměnné vytvořené pomocí `@set` se obecně používají ve Podmíněná kompilace příkazy, ale lze použít kdekoli v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kódu.  
  
 Příklady deklarací proměnné vypadají takto:  
  
```JavaScript  
  
      @set @myvar1 = 12  
  
@set @myvar2 = (@myvar1 * 20)  
  
@set @myvar3 = @_jscript_version  
```  
  
 Ve výrazech v závorkách jsou podporovány následující operátory:  
  
-   `! ~`  
  
-   `* / %`  
  
-   `+ -`  
  
-   `<< >> >>>`  
  
-   `< <= > >=`  
  
-   `== != === !==`  
  
-   `& ^ |`  
  
-   `&& | |`  
  
 Pokud proměnná se používá předtím, než byla definována, jeho hodnota může být `NaN`. `NaN` můžete zkontrolovat pomocí `@if` příkaz:  
  
```JavaScript  
@if (@newVar != @newVar)  
   ...  
```  
  
 Toto funguje, protože `NaN` se jediná hodnota nerovná na sebe sama.  
  
## <a name="requirements"></a>Požadavky  
 V všechny verze aplikace Internet Explorer, ale není v podporované [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on Příkaz](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if – příkaz](../../javascript/reference/at-if-statement-javascript.md)