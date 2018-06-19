---
title: JavaScript – chyby za běhu | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT-32725
- VS.WebClient.Help.SCRIPT7002
- VS.WebClient.Help.SCRIPT1001
- VS.WebClient.Help.SCRIPT16389
- VS.WebClient.HelpSCRIPT50
- VS.WebClient.HelpSCRIPT70
- VS.WebClient.HelpSCRIPT87
- VS.WebClient.HelpSCRIPT65535
- VS.WebClient.HelpSCRIPT445
- VS.WebClient.HelpSCRIPT600
- VS.WebClient.HelpSCRIPT2343
- VS.WebClient.HelpSCRIPT122
- VS.WebClient.HelpSCRIPT28
- VS.WebClient.HelpSCRIPT16386
- VS.WebClient.HelpSCRIPT7015
- VS.WebClient.HelpSCRIPT3
- VS.WebClient.HelpSCRIPT16388
- VS.WebClient.HelpSCRIPT14
- VS.WebClient.HelpSCRIPT12030
- VS.WebClient.HelpSCRIPT12029
- VS.WebClient.HelpSCRIPT1001
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- errors [JavaScript]
- run-time errors, JavaScript
ms.assetid: c111469d-8f31-4bde-9d46-16d58775db7d
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb75c59fae32911c3dd3a7468439a198d7191755
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791751"
---
# <a name="javascript-run-time-errors"></a>JavaScript – chyby za běhu
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]běhové chyby jsou chyby, ke kterým dochází, když se pokusí provést akci, která systém nemůže spustit skript. Když jsou vyhodnocovaný výrazech proměnné nebo se se přidělí paměť, může se zobrazit chyby.  
  
## <a name="windows-runtime-errors"></a>Chyby modulu Windows Runtime  
 Pokud používáte rozhraní API systému Windows Runtime v vaší [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, může zobrazit chyby jazyka JavaScript, které byly převedeny z hodnoty HRESULT Windows Runtime. Hodnoty HRESULT Windows Runtime v rozsahu přes 0x80070000 se převedou na chyby jazyka JavaScript převzetím šestnáctkové hodnoty nízkou bits a převod na datový typ decimal. Například HRESULT 0x80070032 je převedeno na desetinnou hodnotu 50 a chybě jazyka JavaScript je SCRIPT50. HRESULT 0x80074005 je převedeno na desetinnou hodnotu 16389 a chybě jazyka JavaScript je SCRIPT16389.  
  
## <a name="errors"></a>Chyby  
  
|Číslo chyby|Popis|  
|------------------|-----------------|  
|5|[Přístup byl odepřen.](../../javascript/misc/access-is-denied.md)|  
|438|[Objekt nepodporuje tuto vlastnost nebo metoda](../../javascript/misc/object-doesn-t-support-this-property-or-method.md)|  
|1001|Nedostatek paměti|  
|5029|[Délka pole musí být konečné kladné celé číslo](../../javascript/misc/array-length-must-be-a-finite-positive-integer.md)|  
|5030|[Délka pole musí být přiřazena konečné kladné číslo.](../../javascript/misc/array-length-must-be-assigned-a-finite-positive-number.md)|  
|5028|[Byl očekáván objekt Array nebo arguments](../../javascript/misc/array-or-arguments-object-expected.md)|  
|5010|[Byla očekávána logická hodnota](../../javascript/misc/boolean-expected.md)|  
|5003|[Nelze přiřadit do výsledku funkce](../../javascript/misc/cannot-assign-to-a-function-result.md)|  
|5000|[Nelze přiřadit do objektu 'this'](../../javascript/misc/cannot-assign-to-this.md)|  
|5034|[Cyklický odkaz v argumentu hodnoty není podporován](../../javascript/misc/circular-reference-in-value-argument-not-supported.md)|  
|5006|[Byl očekáván objekt Date](../../javascript/misc/date-object-expected.md)|  
|5015|[Byl očekáván objekt Enumerator](../../javascript/misc/enumerator-object-expected.md)|  
|5022|[Vyvolána výjimka která nebyla zachycena](../../javascript/misc/exception-thrown-and-not-caught.md)|  
|5020|[Očekávaný ')' v regulárním výrazu](../../javascript/misc/expected-right-parenthesis-in-regular-expression-javascript.md)|  
|5019|[Očekává se &#93;' v regulárním výrazu](../../javascript/misc/expected-right-square-bracket-in-regular-expression-javascript.md)|  
|5023|[Funkce nemá platný prototyp objektu.](../../javascript/misc/function-does-not-have-a-valid-prototype-object.md)|  
|5002|[Byla očekávána funkce](../../javascript/misc/function-expected.md)|  
|5008|[Neplatné přiřazení](../../javascript/misc/illegal-assignment-javascript.md)|  
|5021|[Neplatný rozsah ve znakové sadě](../../javascript/misc/invalid-range-in-character-set-javascript.md)|  
|5035|[Neplatný argument nahrazení](../../javascript/misc/invalid-replacer-argument.md)|  
|5014|[Byl očekáván objekt jazyka JavaScript](../../javascript/misc/javascript-object-expected.md)|  
|5001|[Bylo očekáváno číslo](../../javascript/misc/number-expected.md)|  
|5007|[Byl očekáván objekt](../../javascript/misc/object-expected.md)|  
|5012|[Byl očekáván člen objektu](../../javascript/misc/object-member-expected.md)|  
|5016|[Očekáván objekt regulárního výrazu](../../javascript/misc/regular-expression-object-expected.md)|  
|5005|[Očekáván řetězec](../../javascript/misc/string-expected.md)|  
|5017|[Chyba syntaxe v regulárním výrazu](../../javascript/misc/syntax-error-in-regular-expression-javascript.md)|  
|5026|[Počet míst za desetinnou čárkou je mimo rozsah.](../../javascript/misc/the-number-of-fractional-digits-is-out-of-range.md)|  
|5027|[Přesnost je mimo rozsah.](../../javascript/misc/the-precision-is-out-of-range.md)|  
|5025|[Dekódovaný identifikátor URI nemá platné kódování](../../javascript/misc/the-uri-to-be-decoded-is-not-a-valid-encoding.md)|  
|5024|[Kódovaný identifikátor URI obsahuje neplatný znak](../../javascript/misc/the-uri-to-be-encoded-contains-an-invalid-character.md)|  
|5009|[Nedefinovaný identifikátor](../../javascript/misc/undefined-identifier.md)|  
|5018|[Neočekávaný kvantifikátor](../../javascript/misc/unexpected-quantifier-javascript.md)|  
|5013|[Byl očekáván objekt VBArray](../../javascript/misc/vbarray-expected.md)|  
  
## <a name="see-also"></a>Viz také  
 [Chyby syntaxe jazyka JavaScript](../../javascript/reference/javascript-syntax-errors.md)