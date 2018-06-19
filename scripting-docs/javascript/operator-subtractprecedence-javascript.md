---
title: Priorita operátorů (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- operator precedence
- order of precedence
ms.assetid: cf3c510a-2214-4b47-b8fe-3521298efaab
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82503a312a4a4996e3bd38f596eef3104af3f11b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789135"
---
# <a name="operator-precedence-javascript"></a>Priorita operátorů (JavaScript)
Priorita operátorů popisuje pravidla, podle kterých se určí pořadí, ve kterém jsou operace prováděny při vyhodnocování výrazu. Operace s vyšší prioritou jsou prováděny před operacemi s nižší prioritou. Například násobení je provedeno před sčítáním.  
  
## <a name="includejavascriptjavascriptincludesjavascript-mdmd-operators"></a>[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] – operátory  
 Následující tabulka uvádí [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] operátory, seřazené od nejvyšší po nejnižší. Operátory se stejnou prioritou jsou vyhodnocovány zleva doprava.  
  
|Operátor|Popis|  
|--------------|-----------------|  
|. [ ] ( )|Přístup k poli, indexování pole, volání funkce a seskupení výrazu|  
|++ -- - ~ ! Odstranit nové typeof void|Unární operátory, vrácení typu dat, vytvoření objektu, nedefinované hodnoty|  
|* / %|Násobení, dělení, modulo dělení|  
|+ - +|Sčítání, odčítání, zřetězení řetězců|  
|<\< >> >>>|Bitové posunutí|  
|< \<= >> = instanceof|Je menší než, je menší než nebo rovno, je větší než, je větší než nebo rovno, instanceof|  
|== != === !==|Rovnost, nerovnost, striktní rovnost a striktní nerovnost|  
|&|Bitový operátor AND|  
|^|Bitový operátor XOR|  
|&#124;|Bitový operátor OR|  
|&&|Logický operátor AND|  
|&#124;&#124;|Logický operátor OR|  
|?:|Podmiňovací operátor|  
|= *OP*=|Přiřazení, přiřazení s operací (třeba += a & =)|  
|,|Vícenásobné vyhodnocení|  
  
 Chcete-li změnit pořadí vyhodnocování stanovené prioritou operátorů, použijte závorky. To znamená, že výraz v závorkách je plně vyhodnocen před použitím jeho hodnoty ve zbývajících částech výrazu.  
  
 Příklad:  
  
```JavaScript  
var result = 78 * 96 + 3;  
document.write(result);  
document.write("<br/>");  
  
result = 78 * (9 + 3);  
document.write(result);  
  
// Output:  
// 7491  
// 936  
```  
  
 V prvním výrazu jsou tři operátory: =, * a +. Souladu s pravidly operátorů jsou vyhodnocovány v následujícím pořadí: \*, +, = (78 \* 96 = 7488, 7488 + 3 = 7491).  
  
 Ve druhém výrazu je operátor () vyčíslen první, takže přidání výrazu je vyhodnoceno před násobením (9 + 3 = 12, 12 * 78 = 936).  
  
 Následující příklad ukazuje příkaz, který zahrnuje celou řadu operátory a překládá se `true`.  
  
```JavaScript  
var num = 10;  
  
if(5 == num / 2 && (2 + 2 * num).toString() === "22") {  
    document.write(true);  
}  
    // Output:  
    // true  
```  
  
 Operátory jsou vyhodnocovány v tomto pořadí: () pro seskupení, *, + (v rámci seskupení), "." pro funkce, () pro funkce, /, ==, ===, a & &.