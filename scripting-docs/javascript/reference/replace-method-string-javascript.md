---
title: "replace – metoda (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: replace
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- replacing strings
- Replace method
ms.assetid: 5f0e4765-df4d-4887-bd09-efe5e58251bf
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82894a5d7f92c8231a6ba3a1948369fb2c819a6d
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="replace-method-string-javascript"></a>replace – metoda (String) (JavaScript)
Nahrazuje text v řetězci regulárním výrazem nebo hledaným řetězcem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringObj.replace(rgExp, replaceText)  
```  
  
## <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. `String` Objekt nebo řetězcový literál, na které se má provést nahrazení. Tento řetězec není upraveném **nahradit** metoda. Vrácená hodnota této metody je řetězec vzniklý nahrazením.  
  
 `rgExp`  
 Požadováno. Instance **regulární výraz** objekt, který obsahuje regulární výraz a příslušné značky. Může být také `String` objekt nebo řetězcový literál, který představuje regulární výraz. Pokud `rgExp` není instance **regulární výraz** objekt, je převedeno na řetězec a hledání přesné se provádí výsledků; žádný pokus se uskuteční převést řetězec na regulární výraz.  
  
 `replaceText`  
 Požadováno. A `String` objekt nebo řetězcový literál obsahující text, který má nahradit pro všechny úspěšné výskyty `rgExp` v `stringObj`. V [!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější, `replaceText` argument může být také funkci, která vrátí Nahrazovací text.  
  
## <a name="return-value"></a>Návratová hodnota  
 Výsledek **nahradit** metoda je kopie `stringObj` po zadaný náhrady byly provedeny.  
  
## <a name="remarks"></a>Poznámky  
 Kterékoli z následujících proměnných shody lze použít k identifikaci poslední shody a řetězce, ze kterého shoda pochází. Proměnné shody lze použít při nahrazování textu, kdy je třeba dynamicky rozlišit náhradní řetězec.  
  
|Znaky|Význam|  
|----------------|-------------|  
|**$$**|`$`([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější)|  
|**$&**|Určuje část `stringObj` celý vzor odpovídající. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější)|  
|`$``|Určuje část `stringObj` který předchází shody popsaného  **$&** . ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější)|  
|`$'`|Určuje část `stringObj` , který následuje shody popsaného  **$&** . ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější)|  
|`$`  ***n***| *n* Tý zachytit submatch, kde  *n*  je jednoduché desetinné číslo od 1 do 9. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější)|  
|`$`  ***nn***| *nn* Tý zachytit submatch, kde  *nn*  je letopočty desetinné číslo od 01 do 99. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] nebo novější)|  
  
 Pokud `replaceText` je funkce, pro každý odpovídající podřetězec funkce je volána s následující *m* + 3 argumenty kde *m* je počet zaznamenávání závorkách v levém `rgExp`. První argument je podřetězec, který byl shodný. Další *m* argumenty jsou všechny záznamy, která byla vygenerována z hledání. Argument *m* + 2 je posun v rámci `stringObj` kde došlo k chybě shody a argument *m* + 3 je `stringObj`. Výsledkem je hodnota řetězce, která vznikla nahrazením každého shodného podřetězce odpovídající návratovou hodnotou volání funkce.  
  
 **Nahradit** metoda aktualizuje vlastnosti na globální `RegExp` objektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **nahradit** metody lze nahradit všechny instance řetězce "the" s "a".  
  
```JavaScript  
var s = "the batter hit the ball with the bat";  
  
// Replace "the" with "a".  
var re = /the/g;  
var result = s.replace(re, "a");  
document.write(result);  
// Output: a batter hit a ball with a bat  
```  
  
 Kromě toho **nahradit** metoda může také nahradit podvýrazy ve vzoru. Následující příklad zaměňuje každý pár slov v řetězci.  
  
```JavaScript  
  
var s = "The quick brown fox jumped over the lazy dog.";  
var re = /(\S+)(\s+)(\S+)/g;  
// Exchange each pair of words.  
var result = s.replace(re, "$3$2$1");  
document.write(result);  
  
// Output:  quick The fox brown over jumped lazy the dog.  
```  
  
 Následující příklad, který funguje v [!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] a novější, ukazuje, jak používat funkci, která vrátí Nahrazovací text. Nahradí všechny instance čísla následované znakem „F“ převodem na stupně Celsia.  
  
```JavaScript  
function f2c(s1) {  
    // Initialize pattern.  
    var test = /(\d+(\.\d*)?)F\b/g;  
  
    // Use a function for the replacement.  
    var s2 = s1.replace(test,  
      function($0,$1,$2)  
           {   
           return((($1-32) * 5/9) + "C");  
           }  
        )  
    return s2;  
}  
document.write(f2c("Water freezes at 32F and boils at 212F."));  
  
// Output: Water freezes at 0C and boils at 100C.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Exec – metoda (regulární výraz)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [Match – metoda (String)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)   
 [Search – metoda (String)](../../javascript/reference/search-method-string-javascript.md)   
 [Test – metoda (regulární výraz)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Programování regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [Alternace a podvýrazy (JavaScript)](http://msdn.microsoft.com/en-us/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [Zpětné odkazy (JavaScript)](http://msdn.microsoft.com/en-us/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)   
 [HTML5 přetažení ukázkové aplikace](http://code.msdn.microsoft.com/Drag-and-drop-e2701a72)