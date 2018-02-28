---
title: "lastIndex – vlastnost (RegExp) (JavaScript) | Microsoft Docs"
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
- lastIndex
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- lastIndex property
ms.assetid: c8ae2a13-6dff-4cbe-b662-aca3d66c2a7f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5e24fe14d335e1494b13518543f56025625de0b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="lastindex-property-regexp-javascript"></a>lastIndex – vlastnost (RegExp) (JavaScript)
Vrátí znak na pozici, kde začíná na další shodu vyhledávaná řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
RegExp.lastIndex  
```  
  
## <a name="remarks"></a>Poznámky  
 Objekt přidružený k této vlastnosti je vždy na globální `RegExp` objektu.  
  
 `lastIndex` Vlastnost od nuly, tedy index prvního znaku rovná nule. Počáteční hodnoty, je -1. Její hodnota je změnit vždy, když je proveden úspěšně shody.  
  
 `lastIndex` Vlastnost je upraveném `exec` a **testování** metody `RegExp` objekt a `match`, **nahradit**, a **rozdělení**metody `String` objektu.  
  
 Následující pravidla platí při hodnoty `lastIndex`:  
  
-   Pokud není nalezena žádná shoda `lastIndex` je nastaven na hodnotu -1.  
  
-   Pokud `lastIndex` je větší než délka řetězce, **testování** a `exec` nezdaří a `lastIndex` je nastaven na hodnotu -1.  
  
-   Pokud `lastIndex` je rovna délce řetězec regulárního výrazu shody, pokud vzor odpovídá prázdný řetězec. Jinak shoda se nezdaří a `lastIndex` se resetuje na hodnotu -1.  
  
-   V opačném `lastIndex` je nastaven na další pozici následující nejnovější shody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `lastIndex` vlastnost. Tato funkce opakuje hledaný řetězec a vytiskne **index** a `lastIndex` hodnoty pro každého slova v řetězci.  
  
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
      document.write (arr.index + "-" + re.lastIndex + " ");  
      document.write (arr);  
      }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)