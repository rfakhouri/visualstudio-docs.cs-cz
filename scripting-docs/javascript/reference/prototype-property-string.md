---
title: "prototype – vlastnost (String) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 437ce478-9c45-45f7-8952-bd71856cfcd8
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df8c6abbd64fce9172d805c2e22dee51f4fbbee4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-string"></a>prototype – vlastnost (String)
Vrátí odkaz na prototypu pro třídu řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
string.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `string` Argument je název řetězce.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `String` objektu, která vrátí hodnotu posledním elementem řetězce, deklarovat funkci, přidejte ho do `String.prototype`a pak jeho pomocí.  
  
```JavaScript  
function string_last( ){  
    return this.charAt(this.length - 1);  
}  
String.prototype.last = string_last;  
var myString = new String("every good boy does fine");  
document.write(myString.last());  
  
// Output:  
// e  
```  
  
 Všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty mají `prototype` vlastnost, která je jen pro čtení. Vlastnosti a metody mohou být přidány do prototyp, ale objekt nesmí být přiřazena různých prototypu. Uživatelem definované objekty však může přiřadit nový prototypu.  
  
 Seznamy metod a vlastností pro každý vnitřní objekt v této referenční informace k jazyku znamenat ty, které jsou součástí objektu prototypu a které nejsou.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]