---
title: prototype – vlastnost (Date) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 44f9c637-7da7-4833-906d-358506f32ced
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c0b337964d2a2fe17a4e9a7906d81069470e61b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791274"
---
# <a name="prototype-property-date"></a>prototype – vlastnost (Date)
Vrátí odkaz na prototypu pro datum.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
date.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `date` Argument je název objektu.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které na datum. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Date` objektu, která vrátí hodnotu největší elementu pole, deklarovat funkci, přidejte ho do `Date.prototype`a pak jeho pomocí.  
  
```JavaScript  
function max( ){  
    var max = new Date();  
    max.setFullYear(2200, 01, 01);  
    return max;  
}  
Date.prototype.maxDate = max;  
var myDate = new Date();  
  
if (myDate < myDate.maxDate())  
    document.write("today isn't the max");  
else if (myDate == myDate.maxDate())  
    document.write("today is the max");   
  
// Output:  
// today isn't the max  
  
```  
  
 Všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty mají `prototype` vlastnost, která je jen pro čtení. Vlastnosti a metody mohou být přidány do prototyp, ale objekt nesmí být přiřazena různých prototypu. Uživatelem definované objekty však může přiřadit nový prototypu.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]