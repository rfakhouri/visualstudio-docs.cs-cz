---
title: RegExp – objekt (JavaScript) | Microsoft Docs
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
- RegExp
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- RegExp object, overview
- RegExp object
ms.assetid: 7f6b1073-8cbb-49ed-94b6-56833ba663c5
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7319e4556721bcfd397061ce525acfb3278c6b9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791745"
---
# <a name="regexp-object-javascript"></a>RegExp – objekt (JavaScript)
Odpovídá vnitřní globální objekt, který obsahuje informace o výsledcích regulární výraz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
RegExp.property   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované *vlastnost* argument může být některého z `RegExp` vlastnosti objektu.  
  
 `RegExp` Objekt nelze vytvořit přímo, ale je vždy k dispozici pro použití. Dokud se nedokončí hledání úspěšné regulární výraz počáteční hodnoty různé vlastnosti `RegExp` objekt jsou následující:  
  
|Vlastnost|Sdružená vlastnost|Počáteční hodnota|  
|--------------|---------------|-------------------|  
|index||-1|  
|vstup|$_|Prázdný řetězec.|  
|lastIndex –||-1|  
|lastmatch –|$&|Prázdný řetězec.|  
|lastparen –|$+|Prázdný řetězec.|  
|leftcontext –|$`|Prázdný řetězec.|  
|rightcontext –|$'|Prázdný řetězec.|  
|$1 - $9|$1 - $9|Prázdný řetězec.|  
  
 Jeho vlastnosti mít nedefinovaný jako jejich hodnoty, dokud se nedokončí hledání úspěšné regulární výraz.  
  
 Na globální `RegExp` objekt Nezaměňovat s **regulární výraz** objektu. I když jejich zvukových jako samé, jsou samostatné a distinct. Vlastnosti na globální `RegExp` objekt obsahovat průběžně aktualizované informace o každé shody jako dochází při vlastnosti **regulární výraz** objektu obsahují jenom informace o shodách, ke kterým došlo k této instanci systému **regulární výraz**.  
  
## <a name="example"></a>Příklad  
 Následující příklad provádí hledání regulárního výrazu. Zobrazí odpovídá a submatches z na globální `RegExp` objekt a z pole, která je vrácena `exec` metoda.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<a name="js56jsobjregexpprop"></a>   
## <a name="properties"></a>Vlastnosti  
 [$1... $9 – vlastnosti](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md) &#124; [index – vlastnost](../../javascript/reference/index-property-regexp-javascript.md) &#124; [input – vlastnost](../../javascript/reference/input-property-dollar-regexp-javascript.md) &#124; [lastIndex – vlastnost](../../javascript/reference/lastindex-property-regexp-javascript.md) &#124; [lastmatch – vlastnost](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md) &#124; [lastparen – vlastnost](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md) &#124; [leftcontext – vlastnost](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md) &#124; [rightcontext – vlastnost](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)  
  
## <a name="methods"></a>Metody  
 `RegExp` Objekt nemá žádné metody.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)