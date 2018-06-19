---
title: Exec – metoda (regulární výraz) (JavaScript) | Microsoft Docs
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
- exec
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- matching strings
- Exec method
ms.assetid: 83092452-60cc-4218-b4ae-af9e3cb96c34
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 426cc1a8162b03090289cf737a03d64a75df77e9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790620"
---
# <a name="exec-method-regular-expression-javascript"></a>exec – metoda (regulární výraz) (JavaScript)
Provede vyhledávání na řetězec pomocí regulárního výrazu a vrátí pole obsahující výsledky vyhledávání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
rgExp.exec(str)   
```  
  
## <a name="parameters"></a>Parametry  
 `rgExp`  
 Požadováno. Instance **regulární výraz** objekt, který obsahuje regulární výraz a příslušné značky.  
  
 `str`  
 Požadováno. `String` Objekt nebo řetězcový literál, na které se má provést hledání.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `exec` metoda nenajde shody, vrátí `null`. Pokud se najde shoda, `exec` vrátí pole a vlastnosti na globální `RegExp` objekt jsou aktualizovány s ohledem na výsledky shody. Element nula pole obsahuje celou shodu při elementy 1 -  *n*  obsahovat žádné submatches, k nimž došlo v rámci shody. Toto chování je stejný jako u chování `match` metoda bez příznak globální (**g**) nastavit.  
  
 Pokud je globální nastavený příznak pro regulární výraz, `exec` vyhledá řetězec, který začíná na pozici indikován hodnotu `lastIndex`. Pokud není nastavený příznak globální, `exec` ignoruje hodnotu `lastIndex` a hledání od začátku řetězce.  
  
 Poli vráceném `exec` metoda má tři vlastnosti **vstupní**, **index** a **lastIndex –.** **Vstupní** vlastnost obsahuje vyhledávaná celý řetězec. **Index** vlastnost obsahuje umístění odpovídající podřetězec v rámci dokončení vyhledávaná řetězce. `lastIndex` Vlastnost obsahuje umístění za jeho poslední znak v shody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `exec` metoda:  
  
```JavaScript  
function RegExpTest()  
{  
   var ver = Number(ScriptEngineMajorVersion() + "." + ScriptEngineMinorVersion())  
   if (ver < 5.5)  
   {  
      document.write("You need a newer version of JavaScript for this to work");  
      return;  
   }  
  
   var src = "The quick brown fox jumps over the lazy dog.";  
  
   // Create regular expression pattern with a global flag.  
   var re = /\w+/g;  
  
   // Get the next word, starting at the position of lastindex.  
   var arr;  
   while ((arr = re.exec(src)) != null)  
      {  
      // New line:  
      document.write ("<br />");    
      document.write (arr.index + "-" + arr.lastIndex + " ");  
      document.write (arr[0]);  
      }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Match – metoda (String)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [Search – metoda (String)](../../javascript/reference/search-method-string-javascript.md)   
 [Test – metoda (regulární výraz)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Programování regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)