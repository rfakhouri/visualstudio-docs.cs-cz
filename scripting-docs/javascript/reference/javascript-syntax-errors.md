---
title: Chyby syntaxe jazyka JavaScript | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- errors [JavaScript]
- syntax errors, JavaScript
ms.assetid: 0343dc19-5f5e-4a4c-83da-630b4fbcb3b6
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3bc3398d6a90ef308fd2b4b367bc1006ad95f5b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="javascript-syntax-errors"></a>Chyby syntaxe jazyka JavaScript
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]chyby syntaxe dojít při strukturu jednoho z vaší [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] příkazy porušuje jeden nebo více pravidel syntaktické.  
  
## <a name="errors"></a>Chyby  
  
|Číslo chyby|Popis|  
|------------------|-----------------|  
|1019|[Nemůže mít 'break' uveden mimo smyčku](../../javascript/misc/can-t-have-break-outside-of-loop.md)|  
|1020|[Nemůže mít 'continue' uveden mimo smyčku](../../javascript/misc/can-t-have-continue-outside-of-loop.md)|  
|1030|[Podmíněná kompilace je vypnutá.](../../javascript/misc/conditional-compilation-is-turned-off.md)|  
|1027|["default" může být pouze jednou v příkazu 'switch'](../../javascript/misc/default-can-only-appear-once-in-a-switch-statement.md)|  
|1005|[Očekávaný ' ('](../../javascript/misc/expected-left-parenthesis-javascript.md)|  
|1006|[Očekává se).](../../javascript/misc/expected-right-parenthesis-javascript.md)|  
|1012|[Očekávaný '/'](../../javascript/misc/expected-minus.md)|  
|1003|[Očekává se:.](../../javascript/misc/expected-colon.md)|  
|1004|[Očekávaný ';'](../../javascript/misc/expected-semicolon.md)|  
|1032|[Očekávaný ' @'](../../javascript/misc/expected-at.md)|  
|1029|[Očekává se@end.](../../javascript/misc/expected-at-end.md)|  
|1007|[Očekává se &#93;.](../../javascript/misc/expected-right-square-bracket.md)|  
|1008|[Očekávaný ' {'](../../javascript/misc/expected-left-curly-brace.md)|  
|1009|[Očekává se}.](../../javascript/misc/expected-right-curly-brace.md)|  
|1011|[Očekávaný '='](../../javascript/misc/expected-equal-javascript.md)|  
|1033|[Očekávaný 'catch'](../../javascript/misc/expected-catch.md)|  
|1031|[Byla očekávána konstanta](../../javascript/misc/expected-constant.md)|  
|1023|[Byla očekávána šestnáctková číslice](../../javascript/misc/expected-hexadecimal-digit.md)|  
|1010|[Byl očekáván identifikátor](../../javascript/misc/expected-identifier-javascript.md)|  
|1028|[Byl očekáván identifikátor, řetězec nebo číslo](../../javascript/misc/expected-identifier-string-or-number.md)|  
|1024|[Očekávaný 'while'](../../javascript/misc/expected-while.md)|  
|1014|[Neplatný znak](../../javascript/misc/invalid-character-javascript.md)|  
|1026|[Návěstí nebylo nalezeno](../../javascript/misc/label-not-found.md)|  
|1025|[Návěstí bylo předefinováno](../../javascript/misc/label-redefined.md)|  
|1018|['return' mimo funkci – příkaz](../../javascript/misc/return-statement-outside-of-function.md)|  
|1002|[Chyba syntaxe](../../javascript/misc/syntax-error-javascript.md)|  
|1035|[Throw musí být následováno výrazem na stejném řádku zdroje](../../javascript/misc/throw-must-be-followed-by-an-expression-on-the-same-source-line.md)|  
|1016|[Neukončený komentář](../../javascript/misc/unterminated-comment.md)|  
|1015|[Neukončená řetězcová konstanta](../../javascript/misc/unterminated-string-constant-javascript.md)|  
  
### <a name="script-host-errors"></a>Chyby skriptu hostitele  
 Tyto chyby jsou správně hovořícího chyby týkající se hostitelský modul pro skripty, ale se může občas zobrazit.  
  
|Chyba|HRESULT|Popis|  
|-----------|-------------|-----------------|  
|SCRIPT_E_RECORDED –|0x86664004|Chyba byla zaznamenána předávané mezi skriptovací stroj a hostitelem. Hostitel musí předat volající kód chyby.|  
|SCRIPT_E_REPORTED –|0x80020101|Skriptovací stroj ohlásil k hostiteli prostřednictvím IActiveScriptSite::OnScriptError k neošetřené výjimce. Tuto chybu můžete ignorovat hostitele.|  
|SCRIPT_E_PROPAGATE –|0x8002010|Chyba skriptu je rozšířen volajícího, což může být v jiném podprocesu. Hostitel musí předat volající kód chyby.|  
  
## <a name="see-also"></a>Viz také  
 [JavaScript – chyby za běhu](../../javascript/reference/javascript-run-time-errors.md)