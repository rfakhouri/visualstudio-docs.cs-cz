---
title: "indexOf – metoda (String) (JavaScript) | Microsoft Docs"
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
- indexOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- indexOf method, string
- string, indexOf method
ms.assetid: a17372fa-669b-471b-9240-46927a265152
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ecd96acb21f9d7711f9ee00dbf1c1bb70705c0d8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="indexof-method-string-javascript"></a>indexOf – metoda (String) (JavaScript)
Vrátí pozici prvního výskytu podřetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
strObj. indexOf(subString[, startIndex])  
```  
  
## <a name="parameters"></a>Parametry  
 `strObj`  
 Požadováno. A `String` objekt nebo řetězcový literál.  
  
 `subString`  
 Požadováno. Podřetězec hledaný v řetězci  
  
 `startIndex`  
 Volitelné. Index, kdy má začít prohledávat `String` objektu. Je-li tento parametr vynechán, vyhledávání začne od začátku řetězce.  
  
## <a name="remarks"></a>Poznámky  
 **IndexOf** metoda vrátí začátek podřetězce v `String` objektu. Není-li podřetězec nalezen, je vrácena hodnota -1.  
  
 Pokud `startindex` záporné, `startindex` je považován za nula. Je-li větší než nejvyšší index, je považován za nejvyšší index.  
  
 Hledání je prováděno zleva doprava. Jinak tato metoda je stejný jako **lastIndexOf**.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **indexOf** metoda.  
  
```JavaScript  
var str = "original equipment manufacturer";  
  
var s = "equip is at position " + str.indexOf("equip");  
s += "<br />";  
s += "abc is at position " + str.indexOf("abc");  
  
document.write(s);  
  
// Output:  
// equip is at position 9  
// abc is at position -1  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Metoda lastIndexOf (řetězec)](../../javascript/reference/lastindexof-method-string-javascript.md)   
 [Posouvání, posouvání a přibližování ukázkové aplikace](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)