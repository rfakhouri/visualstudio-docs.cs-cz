---
title: "Match – metoda (String) (JavaScript) | Microsoft Docs"
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
- match
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Match method
ms.assetid: eda9ad27-4f9b-4cb1-8345-a0ae85979ca0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46727942d73779351f1c0cceaf2eb90a691a8ebe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="match-method-string-javascript"></a>match – metoda (String) (JavaScript)
Odpovídá řetězci s regulárním výrazem a vrátí pole obsahující výsledky vyhledávání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringObj.match(rgExp)   
```  
  
## <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. `String` Objekt nebo řetězcový literál, na které se má provést hledání.  
  
 `rgExp`  
 Požadováno. Objekt regulárního výrazu, který obsahuje regulární výraz a použít příznaky. Také to může být název proměnné nebo řetězcový literál, který obsahuje regulární výraz a příznaky.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `match` metoda nenajde shody, vrátí `null`. Pokud se najde shoda, `match` vrátí pole a vlastnosti na globální `RegExp` objekt jsou aktualizovány s ohledem na výsledky shody.  
  
 Pokud globální příznak (`g`) není nastavena, Element nula pole obsahuje celou shodu při prvků 1 prostřednictvím  *n*  obsahovat žádné submatches. Toto chování je stejné jako chování [Exec – metoda (regulární výraz)](../../javascript/reference/exec-method-regular-expression-javascript.md) Pokud není nastaven příznak globální. Pokud je globální nastavený příznak, prvků 0 prostřednictvím  *n*  obsahovat všechny shody, které došlo k chybě.  
  
 Pokud není globální příznak nastaven, poli vráceném `match` metoda má dvě vlastnosti `input` a `index`. `input` Vlastnost obsahuje vyhledávaná celý řetězec. `index` Vlastnost obsahuje umístění odpovídající podřetězec v rámci dokončení vyhledávaná řetězce.  
  
 Pokud příznak `i` není nastaven, hledání nerozlišuje malá a velká písmena.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `match` metoda.  
  
```JavaScript  
var src = "azcafAJAC";  
  
var re = /[a-c]/;  
  
var result = src.match(re);  
  
// The entire match is in array element 0.  
document.write(result[0] + "<br/>");  
  
// Now try the same match with the global flag.  
var reg = /[a-c]/g;  
result = src.match(reg);  
  
// The matches are in elements 0 through n.  
for (var index = 0; index < result.length; index++)  
{  
    document.write ("submatch " + index + ": " +  result[index]);  
    document.write("<br />");  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Exec – metoda (regulární výraz)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)   
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [replace – metoda (String)](../../javascript/reference/replace-method-string-javascript.md)   
 [Search – metoda (String)](../../javascript/reference/search-method-string-javascript.md)   
 [Test – metoda (regulární výraz)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Programování regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [Alternace a podvýrazy (JavaScript)](http://msdn.microsoft.com/en-us/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [Zpětné odkazy (JavaScript)](http://msdn.microsoft.com/en-us/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)